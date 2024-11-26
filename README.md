Django Inventory Management System
A cloud-based inventory management system developed with Django and AWS services. This project aims to automate inventory tracking, order management, and reporting to help small and medium-sized enterprises (SMEs) manage their operations efficiently. The system supports real-time stock updates, low-stock notifications, and provides detailed reports on sales, inventory, and order status.

Features
Real-time Inventory Management: Tracks stock levels and updates inventory in real-time.
Low-Stock Notifications: Automated alerts when stock levels fall below a predefined threshold.
Order Management: Manage orders with an intuitive interface. Easily view, update, and track order statuses.
Reporting: Generate detailed reports on stock levels, sales, order statuses, and other metrics.
User Authentication: Secure login and sign-up functionality with role-based access control.
Technologies Used
Django: Web framework for rapid development.
AWS (Amazon Web Services): Hosting and cloud services.
Amazon S3: Used for static file hosting (CSS, images).
Amazon RDS: Relational database service for storing inventory and order data.
AWS Lambda: Serverless functions for triggering low-stock alerts.
AWS IAM: Identity and Access Management for user authentication.
PostgreSQL: Database used for storing application data (orders, products, etc.).
Bootstrap: For front-end UI components.
Chart.js: For visualizing inventory and order data in charts.
Installation
To set up the project on your local machine, follow these steps:

1. Clone the repository
bash
Copy code
git clone https://github.com/zubair-smd/Django-Inventory-mgt.git
2. Set up the virtual environment
bash
Copy code
cd Django-Inventory-mgt
python3 -m venv venv
source venv/bin/activate  # On Windows, use 'venv\Scripts\activate'
3. Install dependencies
bash
Copy code
pip install -r requirements.txt
4. Set up the database
Run the following commands to create the database tables:

bash
Copy code
python manage.py migrate
5. Create a superuser (for accessing the admin panel)
bash
Copy code
python manage.py createsuperuser
6. Run the development server
bash
Copy code
python manage.py runserver
Now you can access the application at http://127.0.0.1:8000/.

AWS Configuration
Setting up AWS services
To set up the cloud infrastructure:

Amazon S3: Configure Amazon S3 for static file hosting (CSS, images).
Amazon RDS: Set up RDS for database hosting. Update the DATABASES setting in settings.py with your RDS instance details.
AWS Lambda: Set up Lambda functions for low-stock alerts.
IAM: Configure AWS IAM roles for securing access to services.
AWS Lambda Integration
To send low-stock notifications, Lambda functions are triggered based on certain events, using the following Python code:

python
Copy code
def notify_low_stock():
    low_stock_items = Product.objects.filter(quantity__lt=10)
    for item in low_stock_items:
        print(f"Low stock alert for {item.name}!")
Usage
Once the application is running, you can access the following features:

Sign Up / Log In: Create a new user or log in to the application.
Dashboard: View a comprehensive dashboard with real-time inventory and order statistics.
Products: Add, edit, or delete products. View product details including stock levels.
Inventory: View detailed information about your current inventory.
Orders: Track the status of orders, from pending to completed.
Reports: Generate detailed reports on sales, inventory levels, and order statuses.
