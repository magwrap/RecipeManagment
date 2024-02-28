# Post-Class: Recipe Management System
Group Project: Recipe Management System
### Objective:
Develop a console application that allows users to manage their cooking recipes. The
application will enable users to create, view, update, and categorize recipes, as well as search for
recipes based on ingredients or categories. The system will also feature category management,
enabling users to organize recipes into different categories and manage these categories (create
new ones, update or delete existing ones, and reassign recipes to different categories). Recipes
must be updated to reflect category changes. If you delete a category, recipes under that
category should be put under a “Default” category. Data persistence will be achieved through
JSON files, allowing users to maintain their recipe collections across sessions. The project
requires collaborative coding using Git and ensures code quality through unit testing with xUnit.
### Required Components:
1. IRecipe Interface
Specifies methods for adding, viewing, updating, and categorizing recipes.
2. IRecipeStorage Interface
Specifies methods for loading and saving recipe data.
3. Recipe Class
Properties: Recipe ID (Guid), Title (string), Ingredients (List), Instructions
(string), Category (string).
ID uses the type Guid (i.e., public Guid ID { get; set; } =
Guid.NewGuid();).
Constructor initializes a recipe with provided details.
4. RecipeManager Class
Implements the IRecipe interface, managing a list of Recipe objects.
Includes functionality to add, update, categorize, and search for recipes.
5. JsonRecipeStorage Class
Implements the IRecipeStorage interface, handling persistence by reading
from and writing to a recipes.json file.
6. Program Class (User Interface)
Post-Class: Recipe Management System
Provides a console-based UI for user interaction, enabling recipe
management operations.
### Technical Requirements:
- JSON Data Persistence: Implement with System.Text.Json to manage recipe data effectively.
- Robust Recipe Management: Include methods in RecipeManager for comprehensive recipe handling.
- Exception Handling and Input Validation: Ensure user-friendly error management for data and operations.
- Git for Collaborative Coding: Utilize Git for version control, emphasizing regular commits and proper workflow practices.
- xUnit Testing: Integrate xUnit for unit testing, covering all functionalities including recipe and category management.
### xUnit Testing Requirements:
- Unit Tests Setup: 
    - Establish a separate xUnit test project within the solution. Reference the main project to access the Recipe Management System's functionalities
- Recipe Class Tests:
    - Constructor_AssignsCorrectValues: Ensure the constructor correctly assigns ID, title, ingredients, instructions, and category.
    - Property_SettersAndGetters: Test all properties for correct data assignment and retrieval.
- RecipeManager Class Tests:
    - AddRecipe_AddsRecipeToList: Verify that a new recipe is correctly added to the list.
    - UpdateRecipe_UpdatesExistingRecipe: Ensure that an existing recipe can be updated with new details.
    - DeleteRecipe_RemovesRecipeFromList: Test that a recipe can be successfully removed from the list.
    - GetRecipe_ReturnsCorrectRecipe: Confirm that the correct recipe is returned when searched by ID.
    - SearchRecipes_FiltersByCategory: Check that the search function correctly filters recipes by category.
    - SearchRecipes_FiltersByIngredient: Ensure recipes can be filtered correctly by ingredients.
    - CategorizeRecipes_AssignsCorrectCategory: Test that recipes can be correctly assigned to new or existing categories.
    - UpdateCategory_UpdatesExistingCategory: Verify that an existing category can be updated with new details (such as a new name).
    - DeleteCategory_RemovesCategoryAndReassignsRecipes: Ensure that deleting a category removes it from the list and appropriately reassigns recipes to a default or specified category.
- JsonRecipeStorage Class Tests:
    - LoadRecipes_LoadsDataFromFile: Test loading recipes from a JSON file.
    - SaveRecipes_SavesDataToFile: Ensure that recipes and categories are correctly saved to a JSON file.
    - LoadRecipes_ThrowsExceptionOnInvalidData: Verify proper exception handling when loading corrupt or invalid JSON data.
- Integration and Continuous Testing:
    - Configure continuous integration (CI) using GitHub Actions to automate running of xUnit tests on every commit to ensure code integrity.
    - There is a note on getting this implemented in a separate document.
### Example Workflow:
1. Application Initialization:
The application starts by loading existing recipe data from recipes.json.
If the file does not exist, it initializes with an empty list of recipes.
After recipes are loaded, or during recipe load, unique categories of the
recipes will be stored in an appropriate data structure.
2. Main Menu Presentation:
Users are presented with a menu to perform various actions: add a new
recipe, view all recipes, update an existing recipe, search for recipes,
manage recipe categories, or exit the application.
3. Adding a New Recipe:
When adding a recipe, the user is prompted to enter details such as title,
ingredients, instructions, and category. These details are then used to
create a new recipe entry in the list.
4. Viewing All Recipes:
 Post-Class: Recipe Management System
Selecting this option displays the entire list of recipes. Users can choose to
view all recipes as is or apply filters to see only recipes from a specific
category or containing certain ingredients.
5. Updating an Existing Recipe:
This function allows users to select an existing recipe and modify any of its
details, including the title, ingredients, instructions, and its assigned
category.
6. Searching for Recipes:
Provides functionality for users to find recipes based on specific
ingredients or by selecting a particular category. This helps users locate
recipes based on their current needs or what they have on hand.
7. Managing Recipe Categories:
This dedicated feature allows users to create new categories, rename
existing ones, delete categories, and reassign recipes to different
categories. Recipes must be updated to reflect the changes. If categories
are deleted, have a “Default” category they are reassigned to.
8. Exiting the Application:
When exiting, the application saves the current state of all recipes and
categories to the recipes.json file, ensuring that all changes are
preserved for the next session.
