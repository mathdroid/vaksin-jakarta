# vaksin api jakarta

because API service vaksinasi-corona.jakarta.go.id is sometime laggy, I made mirror API that simplify the data

I deploy this at `https://vaksin-jakarta.yggdrasil.id/`

data is included the vaccine location include with the schedule same with this https://twitter.com/mathdroid/status/1411712464916414467

# requirements
pip
pipenv
pm2

# install
1. pipenv instyall --deploy --system

## to run scrape for every 5 minutes
`pm2 start ./scrape.py --interpreter python3 --cron "*/5 * * * *" --name scrape-vaksin-jakarta --watch`

## to run the web server
`pm2 start ./main.py --interpreter python3 --name vaksin-api`

## Data Format

```
{
    "kode_lokasi_vaksinasi": 1052,
    "nama_lokasi_vaksinasi": "POS KESEHATAN RUSUNAWA MARUNDA",
    "alamat_lokasi_vaksinasi": "Jl. Marunda Cluster B Blok 8 Lt Dasar RT 16/07",
    "wilayah": "KOTA ADM. JAKARTA UTARA",
    "kecamatan": "CILINCING",
    "kelurahan": "MARUNDA",
    "rt": "16",
    "rw": "7",
    "kodepos": "",
    "jenis_faskes": "Puskesmas",
    "email": "",
    "no_wa_pic": "",
    "jumlah_tim_vaksinator": 1,
    "nama_faskes": "POS KESEHATAN RUSUNAWA MARUNDA",
    "created_at": null,
    "updated_at": null,
    "pcare": false,
    "jadwal": [
        {
            "id": "2021-07-06",
            "label": "Selasa, 06 Juli 2021",
            "kode_lokasi_vaksinasi": 1052,
            "waktu": []
        }
    ]
}
```