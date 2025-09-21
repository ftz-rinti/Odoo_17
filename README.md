# Student Management Module for Odoo

A custom Odoo module designed to manage students, courses, and related academic information.  
It provides a simple interface to create courses, register students, and view student details grouped by course.

---

## 📦 Features

- Create and manage courses  
- Register students with personal and academic details  
- Assign students to multiple courses  
- View students grouped by their enrolled courses  
- Clean menu structure under **Student Management**  

---

## 🚀 Installation Guide

To install this module in your Odoo environment:

1. **Copy the module folder**
   - Place the `student_management` folder inside your **custom addons** directory.  
     Example:  
     ```bash
     C:\odoo\custom_addons\
     ```
     or on Linux:  
     ```bash
     /odoo/custom_addons/
     ```

2. **Update Odoo configuration**
   - Ensure your `odoo.conf` file includes the custom addons path:  
     ```
     addons_path = /odoo/odoo-server/addons,/odoo/custom_addons
     ```

3. **Restart the Odoo server**
   - Linux/macOS:  
     ```bash
     ./odoo-bin -u student_management
     ```
   - Windows (service):  
     - Open *Services* → Restart the **Odoo** service  

4. **Activate Developer Mode (optional but recommended)**
   - In Odoo, go to **Settings → Activate Developer Mode**

5. **Install the module**
   - Log in as **Administrator**  
   - Navigate to **Apps**  
   - Remove the *Apps filter*  
   - Search for **Student Management**  
   - Click **Install**

---

## 🧪 Testing the Module

1. Navigate to the **Student Management** menu on the Odoo dashboard  
2. Create a **Course** (e.g., "Mathematics")  
3. Add a **Student** and assign them to the course  
4. Open the **Students by Course** view to group students by course  
5. Verify that menus, tree views, and forms work as expected  

---

## ⚡ Challenges and Solutions

### 1. Installation process (Python version mismatch)
- **Issue:** Odoo 17 required Python **3.12.8**, but my system initially had a different version installed.  
- **Solution:** Installed Python 3.12.8 and configured the environment. Once the correct version was set up, the module installation worked without issues.
  
### 2. Virtual environment confusion
- **Issue:** I created a virtual environment (`venv`) but accidentally tried to run Odoo with the global Python environment instead. This caused dependency conflicts and errors.  
- **Solution:** Activated the correct virtual environment before starting Odoo, ensuring that the dependencies installed in the venv were used. Example:  
  ```bash
  # On Linux/macOS
  source venv/bin/activate

  # On Windows
  venv\Scripts\activate
  
### 3. Menus not appearing
- **Issue:** Menus defined in XML did not display.  
- **Solution:** Correctly linked the root menu, then updated the module using `-u student_management`.

### 4. Module not visible in Apps list
- **Issue:** Module did not show up under Apps.  
- **Solution:** Removed the default *Apps filter* and ensured `__manifest__.py` included `"application": True`.
