<!DOCTYPE html>
<html>
  <head>
    <title>SELAMAT DATANG!</title>
    <link rel="stylesheet" href="styles.css" />
  </head>
  <body>
      <h1 class="title">SELAMAT DATANG! </h1>
      <p id="currentTime"></p>
      <script src="script.js"></script>
  </body>
</html><html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>To-Do List</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.5/dist/css/bootstrap.min.css" rel="stylesheet"
        integrity="sha384-SgOJa3DmI69IUzQ2PVdRZhwQ+dy64/BUtbMJw1MZ8t5HZApcHrRKUc4W0kG879m7" crossorigin="anonymous">
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap-icons@1.11.3/font/bootstrap-icons.css">

</head>
<body>
    <div class="container py-5">
        <div class="row">
            <!-- Kolom Kiri: Deskripsi -->
            <div class="col-md-6 mb-4">
                <h2>Pogram Kegiatan Bulanan</h2>
              
                <h2>SMK BINA NUSANTARA</h2>
                <p>Program ini memudahkan Anda mengisi list, mengedit, dan menghapus daftar kegiatan.
                    Setiap klik Simpan akan menambahkan atau memperbarui baris di tabel.
                    Data bisa dicentang saat selesai dikerjakan.</p>
                <ul>
                    <li>Tambah tugas baru</li>
                    <li>Edit tugas yang sudah ada</li>
                    <li>Hapus tugas dari daftar</li>
                </ul>
            </div>
    
            <!-- Kolom Kanan: Form + Tabel -->
            <div class="col-md-6">
                <h2>To-Do List</h2>
    
                <!-- Form To-Do List -->
                <form id="todo-form" class="row g-2 mb-4">
                    <div class="col-7">
                        <input type="text" id="todo-name" class="form-control" placeholder="Nama To-Do" required>
                    </div>
                    <div class="col-5">
                        <input type="date" id="todo-date" class="form-control" required>
                    </div>
                    <div class="col-12">
                        <button type="submit" id="submit-button" class="btn btn-primary w-100">Simpan</button>
                    </div>
                </form>
    
                <!-- Tabel To-Do List -->
                <div class="table-responsive">
                    <table class="table table-bordered table-striped align-middle">
                        <thead class="table-dark">
                            <tr>
                                <th>No</th>
                                <th>Nama To-Do</th>
                                <th>Tanggal</th>
                                <th>Selesai</th>
                                <th>Aksi</th>
                            </tr>
                        </thead>
                        <tbody id="todo-table-body">
                            <!-- Data akan masuk di sini -->
                        </tbody>
                    </table>
                </div>
            </div>
        </div>
    </div>
    
    <!-- JavaScript -->
    <script>
        const form = document.getElementById('todo-form');
        const nameInput = document.getElementById('todo-name');
        const dateInput = document.getElementById('todo-date');
        const tableBody = document.getElementById('todo-table-body');
        const submitButton = document.getElementById('submit-button');

        let todos = [];
        let editIndex = null; // NULL artinya tidak sedang edit

        function renderTable() {
            tableBody.innerHTML = '';

            todos.forEach((todo, index) => {
                const row = document.createElement('tr');
                row.innerHTML = `
            <td>${index + 1}</td>
            <td>${todo.name}</td>
            <td>${todo.date}</td>
            <td><input type="checkbox" ${todo.done ? 'checked' : ''} onclick="toggleDone(${index})"></td>
            <td>
            <button class="btn btn-sm btn-warning me-1" onclick="startEdit(${index})">Edit</button>
            <button class="btn btn-sm btn-danger" onclick="deleteTodo(${index})">Hapus</button>
            </td>`;
                tableBody.appendChild(row);
            });
        }

        function toggleDone(index) {
            todos[index].done = !todos[index].done;
            renderTable();
        }

        function startEdit(index) {
            const todo = todos[index];
            nameInput.value = todo.name;
            dateInput.value = todo.date;
            editIndex = index;
            submitButton.textContent = 'Update'; // Ganti tulisan tombol saat edit
        }

        function deleteTodo(index) {
            todos.splice(index, 1);
            renderTable();
        }

        form.addEventListener('submit', function (e) {
            e.preventDefault();

            const name = nameInput.value.trim();
            const date = dateInput.value;

            if (editIndex === null) {
                // Menambahkan data baru
                todos.push({ name, date, done: false });
            } else {
                // Mengupdate data yang diedit
                todos[editIndex].name = name;
                todos[editIndex].date = date;
                editIndex = null;
                submitButton.textContent = 'Simpan'; // Balik ke Simpan setelah update
            }

            form.reset();
            renderTable();
        });
    </script>

    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.5/dist/js/bootstrap.bundle.min.js" 
    integrity="sha384-SgOJa3DmI69IUzQ2PVdRZhwQ+dy64/BUtbMJw1MZ8t5HZApcHrRKUc4W0kG879m7" crossorigin="anonymous">
    </script>
    
</body>
</html>
