# Day 2/100 – Temporary User Account with Expiry Date

**Platform:** KodeKloud  
**Challenge:** 100 Days of DevOps  
**Topic:** Linux User Management

## 🎯 Task

As part of a temporary assignment to the **Nautilus project**, a developer named `siva` required a temporary user account on **App Server 1** in the Stratos Datacenter.

The requirements were:
- Create a user named `siva` in lowercase.
- Set the account expiry date to `2026-12-07`.
- Verify that the user was created successfully and the expiry date was configured correctly.

## 🛠️ Steps Performed

### 1. Connect to App Server 1

From the jump host, I connected to App Server 1 using SSH:

```bash
ssh tony@stapp01
```

### 2. Create the User Account

Initially, I attempted to create the user without elevated privileges:

```bash
useradd siva
```

This resulted in a permission error because creating system users requires root privileges.

I then used `sudo`:

```bash
sudo useradd siva
```

### 3. Verify User Creation

I verified that the user existed using `getent`:

```bash
sudo getent passwd siva
```

Output:

```text
siva:x:1001:1001::/home/siva:/bin/bash
```

This confirmed that the user account had been created successfully.

### 4. Set the Account Expiry Date

I used the `chage` command with the `-E` option to configure the account expiry date:

```bash
sudo chage -E 2026-12-07 siva
```

### 5. Verify the Expiry Date

Finally, I checked the account's aging information:

```bash
sudo chage -l siva
```

Relevant output:

```text
Account expires : Dec 07, 2026
```

The output confirmed that the account expiry date was set correctly.

## 📚 Key Learnings

- **`ssh`** – Connects to a remote server securely.
- **`useradd`** – Creates a new Linux user account.
- **`sudo`** – Executes a command with elevated privileges when authorized.
- **`getent passwd`** – Retrieves user account information.
- **`chage -E`** – Sets the account expiration date.
- **`chage -l`** – Displays password aging and account expiration information.

### 💡 Important Note

Account expiration and password expiration are different.

- **Account expiration** determines when the account becomes unusable.
- **Password expiration** determines when the user's password must be changed.

In this task, I configured the **account expiry date**, not the password expiry date.

## ✅ Result

Successfully created the lowercase user `siva` on App Server 1 and configured the account to expire on **December 7, 2026**.

#100DaysOfDevOps #KodeKloud #Linux #DevOps #UserManagement #LinuxCommands