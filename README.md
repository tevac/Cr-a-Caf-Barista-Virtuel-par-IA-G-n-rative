# Cr-a-Caf-Barista-Virtuel-par-IA-G-n-rative
Créa-Café utilise l'IA générative pour créer des recettes de café personnalisées en fonction des préférences de goût et des habitudes de consommation des utilisateurs, et offre des conseils de préparation adaptés.
import random

class CoffeeProfile:
    def __init__(self, name, ingredients, preparation):
        self.name = name
        self.ingredients = ingredients
        self.preparation = preparation

class CréaCafé:
    def __init__(self):
        self.coffee_profiles = self._init_coffee_profiles()

    def _init_coffee_profiles(self):
        return [
            CoffeeProfile('Espresso', ['espresso'], 'Brew with 18g of coffee for 25-30 seconds.'),
            CoffeeProfile('Latte', ['espresso', 'steamed milk'], 'Brew espresso, then add steamed milk.'),
            CoffeeProfile('Cappuccino', ['espresso', 'steamed milk', 'foam'], 'Brew espresso, add steamed milk, top with foam.'),
            CoffeeProfile('Sweet Vanilla Latte', ['espresso', 'steamed milk', 'vanilla syrup'], 'Brew espresso, add steamed milk and vanilla syrup.')
        ]

    def get_user_preferences(self):
        taste_preference = input("Do you prefer your coffee sweet, bitter, strong, or light? ")
        consumption_time = input("Do you drink your coffee in the morning, afternoon, or evening? ")
        return taste_preference, consumption_time

    def generate_coffee_recipe(self, taste, time):
        if taste == 'sweet':
            selected_profile = 'Sweet Vanilla Latte'
        elif taste in ['bitter', 'strong']:
            selected_profile = 'Espresso'
        else:
            selected_profile = random.choice(['Latte', 'Cappuccino'])

        for profile in self.coffee_profiles:
            if profile.name == selected_profile:
                return profile
