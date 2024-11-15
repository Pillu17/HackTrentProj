# Mind Full
by Pari Chauhan, Vu Anh Thu Nguyen, Gawshitha Parasuraman
# Recipe Optimizer

The Recipe Optimizer is a Flask-based web application that allows users to adjust recipes according to dietary restrictions and portion sizes. The app enables users to select recipes, modify ingredient quantities, and check for dietary compliance (such as vegetarian, vegan, gluten-free, etc.).

## Features

- **Recipe Scaling:** Adjust ingredient quantities based on the number of adult and child portions.
- **Dietary Restriction Checks:** Filter recipes based on specific dietary restrictions.
- **Ingredient Unit Conversion:** Automatically convert ingredient units based on a predefined conversion table.
- **User Interface:** Simple web interface to input recipe name, portion details, and dietary restrictions.

## Project Structure

```plaintext
Recipe Optimizer
├── routes.py                    # Main Flask routes to handle requests and responses
├── calculator.py                # Functions for calculating adjusted recipe portions and converting units
├── services.py                  # Service functions for loading and searching recipes
├── models.py                    # Recipe class definition and data model for recipes
├── utils.py                     # Helper functions for input validation
├── templates
│   └── home.html                # Frontend HTML template for user interaction
├── recipedatabase.xlsx          # Recipe dataset in Excel format
├── foodrestrictiondatabase.xlsx # Dietary restriction data in Excel format
├── unitconversiondata.xlsx      # Unit conversion data in Excel format
└── run.py                       # Run file to start the Flask app
```

# Installation

1. **Clone the repository**:
   ```bash
   git clone <repository_url>
   cd recipe-optimizer
   ```

2. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

3. **Run the Application**:
   ```bash
   python run.py
   ```

4. **Access the Application**:
   Open a web browser and go to \`http://localhost:5000\`.
   
## Key Components

### Routes (\`routes.py\`)
This file defines the Flask routes:
- **\`/\`**: Renders the home page with a form to input recipe details.
- **\`/optimize_recipe\`**: Processes the form data, applies restrictions, scales ingredients, and responds with the adjusted recipe details.

### Calculator (\`calculator.py\`)
Handles the calculations for adjusting recipe portions based on the number of servings and dietary restrictions.

### Services (\`services.py\`)
Includes helper functions to load recipes from the dataset and perform searches by recipe name.

### Models (\`models.py\`)
Defines the \`Recipe\` class to structure the recipe data, including ingredients, instructions, and dietary restrictions.

### Utilities (\`utils.py\`)
Includes helper functions to validate input data, such as ensuring portion numbers are non-negative.

### Templates (\`templates/home.html\`)
Frontend HTML page where users can enter recipe details, specify dietary restrictions, and view results.

## Usage

1. **Enter Recipe Name**: In the input field, type the recipe name.
2. **Set Portion Sizes**: Enter the number of adult and child portions.
3. **Select Dietary Restrictions**: Choose applicable dietary restrictions, or select "None" if there are no restrictions.
4. **Optimize Recipe**: Click "Optimize Recipe" to generate the adjusted ingredient list and instructions.

## Data Files

- **recipedatabase.xlsx**: Contains recipes with ingredient lists and instructions.
- **foodrestrictiondatabase.xlsx**: Lists ingredients restricted by various dietary needs.
- **unitconversiondata.xlsx**: Conversion data for ingredient units.

## Error Handling

- Provides feedback if a recipe is not found or a dietary restriction is not available.
- Validates that portion sizes are non-negative.

## Future Enhancements

- Additional dietary restrictions.
- Enhanced environmental impact assessment for recipes.
- Improved ingredient conversion options for more complex adjustments.
- Creation of a chatbot that allows users to connect with a dietitian for expert advice on healthy recipes.
- Offering alternative recipes tailored to users' dietary restrictions.
