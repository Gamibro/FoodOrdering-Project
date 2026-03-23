<img src="https://capsule-render.vercel.app/api?type=waving&color=0:ff6b35,100:f7931e&height=220&section=header&text=Food+Ordering+System&fontSize=50&fontColor=ffffff&fontAlignY=38&desc=React+Frontend+--+Admin+Panel&descAlignY=58&descSize=18&animation=fadeIn" width="100%"/>

<div align="center">

[![React](https://img.shields.io/badge/React.js-61DAFB?style=for-the-badge&logo=react&logoColor=black)](https://reactjs.org/)
[![C#](https://img.shields.io/badge/C%23_ASP.NET_MVC-512BD4?style=for-the-badge&logo=dotnet&logoColor=white)](https://dotnet.microsoft.com/)
[![REST API](https://img.shields.io/badge/REST_API-FF6C37?style=for-the-badge&logo=postman&logoColor=white)]()
[![Barcode](https://img.shields.io/badge/Barcode_Scanner-222222?style=for-the-badge&logo=zebra&logoColor=white)]()

> ⚠️ **Note:** This repository contains the **React frontend** of the Food Ordering System.
> The backend is built with **C# ASP.NET MVC** and is maintained in a separate repository.

</div>

---

## 🍽️ About

The **Food Ordering System** is a web application designed to streamline restaurant operations by providing a smart, role-based digital platform for both customers and administrators. The system is split into two user roles — **Admin** and **Customer**.

The **Customer** side allows diners to browse the full restaurant menu, view item sizes, and place orders seamlessly via a **barcode reader** and a **table-based scanner** that identifies the table and links the order directly to it.

The **Admin** side is a comprehensive restaurant management panel covering everything from menu and category management to a detailed **recipe cost calculator** — factoring in overhead costs, labour costs, and ingredient stock prices to automatically compute the production cost of any menu item.

> 📌 This README documents the **Admin Panel (Frontend)** only.

---

## 🏗️ Tech Stack

| Layer | Technology |
|---|---|
| **Frontend** | React.js |
| **Backend** | C# ASP.NET MVC *(separate repository)* |
| **API Communication** | RESTful API |
| **Scanner Integration** | Barcode / Table ID Scanner |

---

## ⚙️ Getting Started

### Prerequisites
- [Node.js](https://nodejs.org/) (v16 or above)
- [npm](https://www.npmjs.com/)

---

### 🚀 Running the Frontend

**1. Clone the repository**
```bash
git clone https://github.com/Gamibro/FoodOrderingSystem.git
```

**2. Navigate to the project directory**
```bash
cd FoodOrderingSystem
```

**3. Install all dependencies**
```bash
npm install
```

**4. Start the development server**
```bash
npm start
```

The app will run at **http://localhost:3000** by default.

> 💡 Make sure the **C# ASP.NET MVC backend** is running on its configured port so that API calls from the frontend resolve correctly.

---

## 🛠️ Admin Panel — Features

The Admin panel is the control centre of the entire restaurant system. It gives the restaurant manager full control over menu items, categories, recipes, cost calculations, and size management.

---

### 🍔 Menu Item Management

The Admin can manage the complete list of food items available in the restaurant.

- ➕ Add new menu items to the system
- ✏️ Edit existing menu item details such as name, description, and category
- 🗑️ Remove menu items that are no longer available
- 📋 View the full list of all menu items currently on the menu

---

### 📏 Menu Item Size Management

Each menu item can be available in **multiple sizes** (e.g. Small, Medium, Large), and the Admin has full control over these sizes per item.

- ➕ Add new sizes for any menu item
- ✏️ Update existing size details
- 🗑️ Remove sizes that are no longer offered
- 📋 View all sizes available for each menu item

---

### 🗂️ Main Food Category Management

The Admin manages the **top-level food categories** that group menu items together (e.g. Burgers, Pizzas, Beverages, Desserts).

- ➕ Add new main food categories
- ✏️ Edit existing category names and details
- 🗑️ Delete categories no longer in use
- 📋 View all main categories in the system

---

### 📁 Sub Item Category Management

Under each main category, the Admin can manage **sub-categories** to further organise the menu (e.g. under Beverages → Hot Drinks, Cold Drinks, Juices).

- ➕ Create sub-categories under any main category
- ✏️ Update sub-category details
- 🗑️ Remove sub-categories as needed
- 📋 View all sub-categories linked to each main category

---

### 📖 Recipe Management & Assignment

The Admin can **create recipes** for each menu item and assign them per size. A single menu item (e.g. a Burger) can have a **different recipe per size** — Small, Medium, or Large — reflecting the different quantities of ingredients used for each.

- 📝 Create a recipe for a specific menu item and size combination
- 🔗 Assign the correct recipe to the corresponding menu item size
- 📋 View all recipes assigned across all menu items and sizes
- ✏️ Update or reassign recipes as the menu evolves

---

### 💰 Recipe Production Cost Calculator

One of the most powerful features of the Admin panel is the **automated production cost calculator**. For every recipe, the Admin inputs three categories of cost along with a profit margin, and the system calculates the **full production cost** of that item automatically.

```
Production Cost = Stock Cost + Overhead Cost + Labour Cost + Profit Margin
```

---

#### 🧂 Stock / Ingredient Cost

The ingredient cost is based on the **raw materials** required to prepare the recipe.

| Input | Description |
|---|---|
| **Stock Item** | The ingredient used (e.g. flour, chicken, oil) |
| **Unit Price** | The price per unit of that ingredient |
| **Stock Quantity** | The quantity of that ingredient used for this recipe |

> 💡 `Stock Cost = Unit Price × Stock Quantity` — summed across all ingredients in the recipe.

---

#### 🔥 Overhead Cost

Overhead costs represent the **indirect operational expenses** incurred while preparing the dish.

| Input | Description |
|---|---|
| **Gas** | Cost of gas used during preparation |
| **Electricity** | Electrical cost for appliances and equipment |
| **Water** | Water usage cost during preparation |

> 💡 All overhead inputs are summed to produce the total overhead cost for the recipe.

---

#### 👨‍🍳 Labour Cost

Labour cost is calculated based on the **staff involved**, their **hourly rate**, and the **time taken** to prepare the recipe.

| Input | Description |
|---|---|
| **Staff Role** | The role involved (e.g. Head Cook, Chef) |
| **Hourly Rate (LKR)** | The wage rate per hour for that role |
| **Preparation Time (minutes)** | Number of minutes that role spends on the dish |

> 💡 `Labour Cost = (Hourly Rate ÷ 60) × Preparation Time` — summed across all staff roles involved.

---

#### 📊 Profit Margin

The Admin sets a **profit margin percentage** per recipe. This is applied on top of the combined costs to arrive at the final production cost.

```
Final Production Cost = (Stock + Overhead + Labour) × (1 + Profit Margin %)
```

This gives the restaurant a precise, data-driven price baseline for every item — ensuring profitability is always accounted for.

---

## ✨ Admin Feature Summary

| Feature | Description |
|---|---|
| 🍔 Menu Item Management | Add, edit, remove, and view all food items |
| 📏 Item Size Management | Manage Small / Medium / Large sizes per item |
| 🗂️ Main Category Management | Organise items into top-level food categories |
| 📁 Sub Category Management | Create nested sub-categories under main ones |
| 📖 Recipe Assignment | Assign unique recipes per menu item per size |
| 🧂 Stock Cost Calculation | Auto-calculate ingredient costs by unit price × quantity |
| 🔥 Overhead Cost Input | Input gas, electricity, and water costs per recipe |
| 👨‍🍳 Labour Cost Calculation | Calculate cook wages based on hourly rate × prep time |
| 📊 Profit Margin Setting | Set item-specific profit margins for pricing |
| 💰 Production Cost Output | Auto-compute total production cost per recipe |





## 📫 Contact

Built by **Gamith Ranasinghe**

📧 [gamithranasinghe001@gmail.com](mailto:gamithranasinghe001@gmail.com)
🔗 [LinkedIn](https://linkedin.com/in/gamith-ranasinghe)
💻 [GitHub](https://github.com/Gamibro)

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:f7931e,100:ff6b35&height=120&section=footer&animation=fadeIn" width="100%"/>
