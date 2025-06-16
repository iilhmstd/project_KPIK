program PendaftaranKIPK;
uses crt;

type
  TKampus = record
    nama: string;
    akreditas: string;
  end;

  TProdi = record
    nama: string;
    akreditas: string;
  end;

var
  nama, alamat, ijazah, SKTM, lanjut: string;
  Jkeluarga: integer;
  pendapatan, tanggungan, IPK: real;
  kampus: TKampus;
  prodi: TProdi;
  lolos: boolean;

function AkreditasiLayak(akre: string): boolean;
begin
  akre := UpCase(akre);
  AkreditasiLayak := (akre = 'A') or (akre = 'B');
end;

function AkreditasiValid(akre: string): boolean;
begin
  akre := UpCase(akre);
  AkreditasiValid := (akre = 'A') or (akre = 'B') or (akre = 'C'); 
end;

begin
  clrscr;
  writeln('========= Pendaftaran Penerima KIP-K =========');
  writeln('~ Tekan Enter untuk melanjutkan ~');
  readln;

  writeln('===== Formulir Pendaftaran ======');
  write('Masukkan nama anda: '); readln(nama);
  write('Masukkan alamat anda: '); readln(alamat);
  writeln('Apakah anda memiliki Ijazah atau SKL?');
  write('(Ya/Tidak): '); readln(ijazah);
 
  if (ijazah = 'YA') or (ijazah = 'ya') or (ijazah = 'Ya') or (ijazah = 'yA') then
  begin
    //
  end
  else
  begin
    writeln('Mohon maaf ', nama, ', anda belum memenuhi persyaratan pendaftaran.');
    readln;
    halt;
  end;

  writeln('Apakah anda memiliki SKTM?');
  write('(Ya/Tidak): '); readln(SKTM);
  if (SKTM = 'YA') or (SKTM = 'ya') or (SKTM = 'Ya') or (SKTM = 'yA') then
    writeln('Pendaftaran berhasil. Silakan lanjut ke tahap seleksi ',  nama, '!')
  else
  begin
    writeln('Mohon maaf, ', nama, ' anda belum memenuhi persyaratan pendaftaran');
    readln;
    halt;
  end;

  writeln;
  writeln('Apakah anda ingin melanjutkan ke proses seleksi KIP-K?');
  write('(Ya/Tidak): '); readln(lanjut);

  if (lanjut = 'Tidak') or (lanjut = 'tidak') or (lanjut = 'TIDAK') then
  begin
    writeln('Terima kasih, semoga sukses!');
    readln;
    halt;
  end;

  clrscr;
  writeln('======= Seleksi Penerimaan Beasiswa KIP-K =======');
  write('masukkan IPK kamu: '); readln(IPK);
  if IPK < 3.5 then
    begin
    write('mohon maaf anda tidak memenuhi persyaratan minimum IPK');
    readln;
    halt;
    end
    else
    begin
      //
    end;

  write('Masukkan jumlah anggota keluarga: '); readln(Jkeluarga);

  if Jkeluarga <= 0 then
    begin
      writeln('Jumlah anggota keluarga tidak valid.');
      readln;
      halt;
    end;

  write('Masukkan total pendapatan orang tua (Rp): '); readln(pendapatan);

  if pendapatan <= 4000000 then
    begin
      // Melanjutkan ke proses seleksi kampus dan prodi, dan menghitung tanggungan
    end
    else
    begin
      tanggungan := pendapatan / Jkeluarga;

      if tanggungan > 750000 then
      begin
        writeln('==================================');
        writeln('Mohon maaf Anda tidak memenuhi syarat untuk melanjutkan seleksi.');
        readln;
        halt;
      end;
    end;

  // Proses Seleksi Kampus dan Program Studi
  clrscr;

  writeln('=== Nama Perguruan Tinggi ===');
  write('Masukkan nama: ');
  readln(kampus.nama);
  writeln;

  repeat
    writeln('=== Akreditas Universitas/Perguruan ===');
    write('Masukkan akreditas (A, B, C): ');
    readln(kampus.akreditas);
    if not AkreditasiValid(kampus.akreditas) then
      writeln('Input tidak valid. Silakan masukkan A, B, C.');
  until AkreditasiValid(kampus.akreditas);
  writeln;

  writeln('=== Nama Program Studi ===');
  write('Masukkan nama: ');
  readln(prodi.nama);
  writeln;

  repeat
    writeln('=== Akreditas Program Studi ===');
    write('Masukkan akreditas (A, B, C): ');
    readln(prodi.akreditas);
    if not AkreditasiValid(prodi.akreditas) then
      writeln('Input tidak valid. Silakan masukkan A, B, C.');
  until AkreditasiValid(prodi.akreditas);
  writeln;

  // Sistem ini untuk penentuan kelulusan 
  lolos := AkreditasiLayak(kampus.akreditas) and AkreditasiLayak(prodi.akreditas);

  writeln('Hasil Seleksi Beasiswa Mandiri KIP-Kuliah');
  writeln('-----------------------------------------');
  writeln('1. Nama: ', nama);
  writeln('2. Alamat: ', alamat);
  writeln('3. Ijazah/SKL: ', ijazah);
  writeln('4. SKTM: ', SKTM);
  writeln('5. Indeks Prestasi Kumulatif: ', IPK:0:2);
  writeln('6. Jumlah Anggota Keluarga: ', Jkeluarga);
  writeln('7. Pendapatan Orang Tua: Rp ', pendapatan:0:0);
  
  if pendapatan <= 4000000 then
    writeln('8. Tanggungan per Anggota Keluarga: Rp ', pendapatan / Jkeluarga:0:0)
  else
    writeln('8. Tanggungan per Anggota Keluarga: Rp ', tanggungan:0:0);

  writeln('9. Nama Perguruan Tinggi: ', kampus.nama);
  writeln('10. Akreditas Universitas: ', kampus.akreditas);
  writeln('11. Nama Program Studi: ', prodi.nama);
  writeln('12. Akreditas Program Studi: ', prodi.akreditas);
  
  if lolos then
    writeln('> SELAMAT ANDA LULUS SELEKSI BEASISWA KIP-KULIAH <')
  else
    writeln('> Mohon maaf, Anda tidak Lolos seleksi. Tetap Semangat yah :) <');

  readln;
end.
