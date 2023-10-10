## **TaskerAppMAUI**

This is a CollectionView focused app led by Hector Perez on his Udemy course: *.NET MAUI course with Visual Studio 2022 creating PROJECTS*

*MainView* is the primary View for displaying the List of tasks:
- Label texts are bound to *MainViewModel*
- The ProgressBar updates when the *Tasks* are checked off
- The tasks themselves are also bound, and implement the *Convert* Converter to transform the *Color* property fom Hex and a DataTrigger that adds a Strikethrough to any checked off *Tasks*
- **Codebehind**
  - *Button_Clicked()* creates an instance of *NewTaskView* with binding to *NewTaskViewModel* and then pushes to *NewTaskView*

*NewTaskView* allows the user to create new *Categories* and *Tasks*, then adds them to *MainView*
- All data is bound, and the buttons house the Events that allow for *Task* and *Category* item creation
- **Codebehind**
  - *AddTaskClicked()* applies the selected *Category*, adds the *Task* to the *Tasks* List, then Pops the View off
    - It also displays an Alert should the user try to add a *Task* without selecting a *Category* and prevents them from doing so
  - *AddCategoryClicked()* displays a Prompt that allows users to enter the name of the *Category* (15 characters max), then assigns a random color by way of utilizing the *Random* Class in *Color.FromRgb()*
 
The ViewModels and Models implement *Fody* for ease of INotifyPropertyChanged, and a custom Style *AppStyles* was created for ease of styling and consistency.
