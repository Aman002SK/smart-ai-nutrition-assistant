🥗 Smart AI Nutrition Assistant 


📌 Project Overview


This project is an AI-based meal planning system that uses a cleaned dataset of Indian recipes, nutritional categorization, and the phi-2 language model to generate personalized meal plans. It allows users to specify dietary preferences, caloric goals, and ingredient preferences to receive structured, healthy meal plans.


🚀 Key Features

Natural language-based meal plan generation using LLM (phi-2).

Embedding-based recipe retrieval with FAISS.

Preprocessed and categorized recipe data (Vegetarian, Vegan, etc.).

FastAPI-ready structure for easy API deployment.

Easily extendable for web or mobile UI integration.

📂 Project Structure

bash
Copy
Edit

├── cleaned_recipes.json             # Cleaned data after removing duplicates
├── categorized_recipes.json         # Recipes with dietary labels
├── recipe_embeddings.npy            # Sentence embeddings of recipes
├── recipe_index.faiss               # FAISS index for similarity search
├── final_recipes.json               # Final data used by the app
├── meal_plan_generator.py           # Code using phi-2 to generate plans
├── requirements.txt                 # Dependencies
└── README.md                        # This file
🧠 Technologies Used
Python

Pandas, NumPy

Sentence-Transformers

FAISS

Hugging Face Transformers (phi-2)

FastAPI (for API layer)

📊 Dataset
Source: Cleaned Indian Food Dataset (Cleaned_Indian_Food_Dataset.json)

Records: 5,928 recipes

Key Columns: TranslatedRecipeName, Cleaned-Ingredients, TranslatedInstructions

🧹 Data Preprocessing
Removed duplicate recipe names

(Optional) Standardized ingredient units (e.g., tsp → teaspoon)

Categorized recipes as: Vegetarian, Non-Vegetarian, Lacto-Vegetarian, Vegan

Generated embeddings using all-MiniLM-L6-v2 for semantic search

🤖 LLM Integration (phi-2)
Prompts the model to generate daily meal plans based on:

Target calories

Diet type

Cuisine

Meals per day

Preferred/Excluded ingredients

💡 How to Run
Install dependencies:

bash
Copy
Edit
pip install -r requirements.txt
Prepare Data:

Run data cleaning and embedding scripts.

Generate FAISS index.

Generate Meal Plan:

python
Copy
Edit
from meal_plan_generator import generate_meal_plan
preferences = {
    "calories": 2000,
    "cuisine": "Indian",
    "diet": "Vegetarian",
    "meals_per_day": 3,
    "preferred_ingredients": ["paneer", "dal", "rice"],
    "excluded_ingredients": ["onion", "garlic"]
}
print(generate_meal_plan(preferences))


🔮 Future Enhancements
Add nutrition breakdown per recipe

Web dashboard using React/Next.js

User feedback loop for refining suggestions

Multilingual recipe support

📚 References
Hugging Face Transformers

FAISS

Sentence Transformers

Phi-2 Model
