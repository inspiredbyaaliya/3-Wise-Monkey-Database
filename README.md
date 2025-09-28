# 3 Wise Monkeys – Inventory Management Database (MySQL)

This repository contains the **MySQL database** developed for the ISBS304 *Information System Project*.  
The system was designed for the **3 Wise Monkeys** hospitality venue in Sydney as part of a barcode-based inventory management solution.  

The database supports **real-time stock tracking, low-stock alerts, automated reordering, and audit logs**.

---

## 📂 Files in This Repo
- `inventory_system_items.sql` – Table schema for items (products, barcodes, categories, suppliers, etc.).
- `inventory_system_reorder_settings.sql` – Reorder thresholds per item for low-stock alerts.
- `inventory_system_stock_log.sql` – Stock movement log (who, what, how much, when).
- `inventory_system_users.sql` – Users table with roles (Admin, Manager, Bartender) and hashed passwords.

---

## 📊 Database Design & Relationships
The design includes **four core tables**:

- **Users** → role-based login (Admin/Manager/Bartender) with secure credentials.  
- **Items** → stores product details, categories, quantities, suppliers, and locations.  
- **Reorder_Settings** → defines minimum stock thresholds; triggers low-stock alerts.  
- **Stock_Log** → audit trail of all stock movements (add/remove), linked to users and items.  

**Relationships (FKs):**
- `Stock_Log.user_id → Users.user_id` (who performed the action)  
- `Stock_Log.item_id → Items.item_id` (which product was updated)  
- `Reorder_Settings.item_id → Items.item_id` (thresholds per item)  

