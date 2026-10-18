# Step 1: Log in to the `stapp03` Server and Create a User

### 1. Connect to the Server

Log in to the `stapp03` server using SSH with the `banner` user.

```bash
ssh banner@stapp03
```

Enter the password for the `banner` user when prompted.

### 2. Create the User

Execute the following command to create a user named `ammar` with `/usr/sbin/nologin` as its login shell.

```bash
sudo useradd -s /usr/sbin/nologin ammar
```

**Explanation:**
- `sudo` — Executes the command with administrative privileges.
- `useradd` — Creates a new user account.
- `-s /usr/sbin/nologin` — Assigns the `nologin` shell, preventing the user from obtaining a normal interactive login shell.
- `ammar` — The username to create.

### 3. Verify the User

Run the following command to verify that the user was created successfully.

```bash
getent passwd ammar
```

**Expected output:**

```text
ammar:x:<UID>:<GID>::/home/ammar:/usr/sbin/nologin
```

The UID and GID will vary depending on the system.

**Verification:** Confirm that the output contains `ammar` and ends with `/usr/sbin/nologin`. This indicates that the user exists and has the intended login shell.