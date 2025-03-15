# **CLEAN SERVER**

* Buat file ```bash
  nano clean.sh```  
  ```bash
  \#\!/bin/bash  
    
  echo "🔍 Mengecek dan membersihkan file sampah di VPS..."  
    
  \# 1\. Hapus log lama yang tidak diperlukan  
  echo "🗑️  Menghapus log lama..."  
  find /var/log \-type f \-name "\*.log" \-delete  
  find /var/log \-type f \-name "\*.gz" \-delete  
  find /var/log \-type f \-name "\*.1" \-delete  
  find /var/log \-type f \-name "\*.old" \-delete  
    
  \# 2\. Bersihkan cache APT (untuk Debian/Ubuntu)  
  echo "🗑️  Membersihkan cache APT..."  
  apt-get clean  
  apt-get autoclean  
    
  \# 3\. Hapus file temporary  
  echo "🗑️  Menghapus file temporary..."  
  rm \-rf /tmp/\*  
  rm \-rf /var/tmp/\*  
    
  \# 4\. Bersihkan Docker (hapus container, image, dan volume yang tidak digunakan)  
  echo "🗑️  Membersihkan Docker..."  
  docker system prune \-af  
    
  \# 5\. Hapus cache pengguna yang tidak digunakan  
  echo "🗑️  Menghapus cache pengguna..."  
  rm \-rf \~/.cache/\*  
    
  \# 6\. Hapus paket lama yang tidak diperlukan  
  echo "🗑️  Menghapus paket lama..."  
  apt-get autoremove \-y  
    
  echo "✅ Pembersihan selesai\!"
  ``` 
    
 ```chmod \+x clean.sh```
    

```./clean.sh```
    
    
  
