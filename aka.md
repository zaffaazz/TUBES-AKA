# TUBES-AKA
TUBES AKA 

# Code AKA mengitung jumlah huruf vocal pada kalimat

import time
import matplotlib.pyplot as plt
from prettytable import PrettyTable

# rekrusif
def hitung_vokal_rekursif(kata, n):
    if n >= len(kata):
        return 0

    huruf = kata[n]
    tambah = 0

    if huruf in 'AaIiUuEeOo':
        tambah += 1

    return tambah + hitung_vokal_rekursif(kata, n + 1)

    # iteratif
def hitung_vokal_iteratif(kata):
    jumlah = 0
    for huruf in kata:
        if huruf in 'AaIiUuEeOo':
            jumlah += 1
    return jumlah

# Grafik untuk menyimpan data
n_values = []
recursive_times = []
iterative_times = []

# Fungsi untuk memperbarui grafik
def update_graph():
    plt.figure(figsize=(8, 6))
    plt.plot(n_values, recursive_times, label='Recursive', marker='o', linestyle='-')
    plt.plot(n_values, iterative_times, label='Iterative', marker='o', linestyle='-')
    plt.title('Performance Comparison: Recursive vs Iterative')
    plt.xlabel('Input (n)')
    plt.ylabel('Execution Time (seconds)')
    plt.legend()
    plt.grid(True)
    plt.show()    

# Fungsi untuk mencetak tabel waktu eksekusi
def print_execution_table():
    table = PrettyTable()
    table.field_names = ["n", "Recursive Time (s)", "Iterative Time (s)"]
    # Use the minimum length of all lists to avoid the IndexError
    min_len = min(len(n_values), len(recursive_times), len(iterative_times))
    for i in range(min_len):
        table.add_row([n_values[i], recursive_times[i], iterative_times[i]])
    print(table)
    
# main
while True:
    kata = input("\nMasukkan satu kata (atau ketik 'stop' untuk selesai): ")

    if kata == "stop":
        update_graph()
        break

    # rekursif
    start = time.time()
    totalRek = hitung_vokal_rekursif(kata, 0)
    durRek = time.time() - start

    # iteratif
    start = time.time()
    totalItr = hitung_vokal_iteratif(kata)
    durItr = time.time() - start

    n = len(kata)
    n_values.append(n)
    recursive_times.append(durRek)
    iterative_times.append(durItr)

    print("Input huruf (n)   :", n)
    print("Jumlah huruf vokal:", totalRek)
    print("Waktu Rekursif    :", durRek, "detik")
    print("Waktu Iteratif    :", durItr, "detik")

    print_execution_table()

  # inputan berupa tabel 
  terdapat inputan solo, jogja, malang, jakarta, surabaya



  # outputan grafik iteratif vs rekursif

  
  





  



 
