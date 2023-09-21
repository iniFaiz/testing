# testing
## tes proyek pyton
```pyton
# Nama: Faiz Alrazi Hidayat
# NIM: 11231025
# Prodi: Informatika
# Tugas: Tugas 2 Algoritma Pemrograman membuat "Validasi Login dengan Python"

# definisi untuk menvalidasi username
def is_valid_username(username):
    if username.isalnum():
        return True
    else:
        print("Username hanya boleh berisi huruf dan angka")
        return False
# definisi untuk menvalidasi password minimal 8 huruf
def is_valid_password(password):
    if len(password) < 8:
        print("Password harus memiliki panjang minimal 8 karakter")
        return False
    # validasi untuk password harus mempunyai karakter, nomor, karakter lowercase, karakter uppercase, dan spasi
    has_letter = any(char.isalpha() for char in password)
    has_digit = any(char.isdigit() for char in password)
    has_lowercase = any(char.islower() for char in password)
    has_uppercase = any(char.isupper() for char in password)
    has_space = ' ' in password
    # output print jika tidak mempunyai salah satu kriteria diatas
    if not (has_letter and has_digit and has_lowercase and has_uppercase and has_space):
        if not has_letter:
            print("Password harus mengandung setidaknya satu huruf")
        if not has_digit:
            print("Password harus mengandung setidaknya satu angka")
        if not has_lowercase:
            print("Password harus mengandung setidaknya satu huruf kecil")
        if not has_uppercase:
            print("Password harus mengandung setidaknya satu huruf besar")
        if  not has_space:
            print("Password harus mengandung setidaknya satu karakter spasi")
        return False
    
    return True
# launch script pertama disini, diatas gunakan hanya sebagai definisi sebuah fungsi
def main():
    username = input("Masukkan username: ")
    password = input("Masukkan password: ")
    
    if is_valid_username(username) and is_valid_password(password):
        print("Login berhasil!")
    else:
        print("Login gagal. Silakan coba lagi.")
# script launch
if __name__ == "__main__":
    main()
    

