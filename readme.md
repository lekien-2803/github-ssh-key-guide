# Hướng dẫn tạo ssh key

## I. Tạo ssh key

### 1. Windows

**1. Mở Git Bash**

Paste đoạn code sau:

```bash
ssh-keygen -t ed25519 -C "lekien.2803.cg@gmail.com"
```

**2. Khi hiện ra thông báo thì bấm `Enter`**

```bash
> Enter file in which to save the key (/c/Users/YOU/.ssh/id_ALGORITHM):[Press enter]
```

**3. Đặt mật khẩu, không muốn mật khẩu thì để trống**

```pwsh
> Enter passphrase (empty for no passphrase): [Type a passphrase]
> Enter same passphrase again: [Type passphrase again]
```

**4. Mở PowerShell quyền admin**
Paste đoạn code sau:

```pwsh
Get-Service -Name ssh-agent | Set-Service -StartupType Manual
```

```pwsh
Start-Service ssh-agent
```

**5. Mở một PowerShell khác không phải quyền admin**

```pwsh
ssh-add c:/Users/YOU/.ssh/id_ed25519
```

### 2. Linux

**1. Mở Terminal**

Paste đoạn code sau:

```bash
ssh-keygen -t ed25519 -C "lekien.2803.cg@gmail.com"
```

**2. Khi hiện ra thông báo thì bấm `Enter`**

```bash
> Enter file in which to save the key (/c/Users/YOU/.ssh/id_ALGORITHM):[Press enter]
```

**3. Đặt mật khẩu, không muốn mật khẩu thì để trống**

```pwsh
> Enter passphrase (empty for no passphrase): [Type a passphrase]
> Enter same passphrase again: [Type passphrase again]
```

**4. Start the ssh-agent in the background.**

```bash
eval "$(ssh-agent -s)"
```

**5. Add your SSH private key to the ssh-agent.**

```bash
ssh-add ~/.ssh/id_ed25519
```

## II. Thêm ssh key vào Git Hub

## 1. Lấy mã

```pwsh
cat ~/.ssh/id_ed25519.pub
```

## 2. Thêm mã vào Git Hub

***Settings -> Access -> SSH and GPG keys -> New SSH key -> Add SSH key***
