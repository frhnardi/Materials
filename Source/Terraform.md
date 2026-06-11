Kamu adalah Senior DevOps / Cloud Engineer dan mentor Infrastructure as Code yang sedang membantu saya membuat materi belajar Terraform untuk teman saya.

KONTEKS:
- Teman saya sedang mengikuti program 3 bulan untuk menjadi DevOps Engineer / Cloud Engineer berbasis AWS.
- Dia sudah belajar:
  1. Basic AWS Core Services
  2. Basic Linux Ubuntu
  3. Git & GitHub
  4. GitHub Actions basic
  5. Docker basic
  6. Monitoring basic
- Sekarang dia masuk materi Terraform sebelum lanjut ke Kubernetes.
- Saya ingin materi Terraform yang compact, tidak terlalu panjang, tapi padat dan sangat practical.
- Output harus berupa 1 file HTML standalone dengan CSS dan JavaScript internal.
- Materi harus menggunakan Bahasa Indonesia, tapi istilah teknis seperti provider, resource, state, module, backend, variable, output, plan, apply tetap pakai istilah aslinya.

PENTING:
- Saya sudah setup AWS MCP Server di Claude Code.
- Untuk bagian AWS resource, kamu WAJIB menggunakan AWS MCP Server untuk memvalidasi dokumentasi AWS terbaru.
- Untuk bagian konsep Terraform, gunakan dokumentasi resmi HashiCorp Terraform dan Terraform Registry terbaru.
- Jangan halusinasi argument Terraform resource.
- Jangan mengarang nama attribute AWS provider.
- Jangan membuat kode Terraform yang terlihat benar tapi belum tervalidasi.
- Kalau AWS MCP Server tidak bisa diakses, beri tahu bahwa validasi AWS via MCP tidak bisa dilakukan.
- Kalau dokumentasi Terraform/Registry tidak bisa diakses, beri tahu bagian mana yang tidak bisa divalidasi.
- Jangan lanjut membuat materi final kalau tidak melakukan validasi dokumentasi minimal.

TUGAS UTAMA:
Buatkan 1 file HTML standalone berisi materi “Terraform Survival Kit for AWS DevOps Beginner”.

GOAL MATERI:
Setelah belajar materi ini, learner harus paham:
- Apa itu Terraform
- Kenapa Terraform penting untuk DevOps / Cloud Engineer
- Cara kerja Terraform basic
- Cara menulis file .tf
- Cara pakai provider AWS
- Cara membuat resource AWS sederhana
- Cara pakai variable dan output
- Cara membaca plan
- Cara apply dan destroy
- Apa itu state
- Apa itu remote backend
- Apa itu module
- Basic best practice Terraform untuk AWS
- Common mistake yang sering terjadi di real project

BATASAN:
- Jangan terlalu panjang.
- Jangan terlalu advanced.
- Jangan bahas Kubernetes.
- Jangan bahas Terragrunt.
- Jangan bahas Terraform Cloud terlalu dalam.
- Jangan bahas enterprise workflow terlalu berat.
- Fokus ke Terraform basic sampai intermediate awal.
- Fokus ke AWS use case.
- Jangan terlalu banyak teori.
- Setiap konsep harus dikaitkan dengan real kerjaan DevOps.

OUTPUT:
- Berikan hanya kode HTML lengkap dari <!DOCTYPE html> sampai </html>.
- Jangan ada markdown.
- Jangan ada penjelasan tambahan di luar kode.
- HTML harus standalone.
- CSS internal.
- JavaScript internal.
- Tidak boleh pakai CDN atau external library.
- Responsive desktop dan mobile.
- Ada animasi ringan.
- Ada sidebar/table of contents.
- Ada progress indicator.
- Ada command block dengan tombol copy.
- Ada accordion.
- Ada mini terminal simulator.
- Ada quiz interaktif dengan skor.
- Ada visual diagram Terraform workflow.
- Ada visual diagram Terraform state.
- Ada section “Docs Verified Notes” yang menjelaskan bagian AWS divalidasi via AWS MCP Server dan bagian Terraform mengacu ke HashiCorp/Terraform Registry official docs.

DESAIN HTML:
Buat seperti interactive DevOps learning dashboard:
- Modern, clean, premium.
- Dark mode friendly.
- Jangan terlihat seperti template default AI.
- Gunakan card-based layout.
- Gunakan warna:
  - Background: #0B1020
  - Surface: #111827
  - Surface raised: #182235
  - Accent purple/indigo untuk Terraform
  - Accent amber/orange untuk AWS
  - Accent green untuk success
  - Accent red untuk danger/warning
  - Text: off-white
- Jangan terlalu ramai.
- Gunakan emoji secukupnya saja.

STRUKTUR MATERI WAJIB:

1. Opening: Kenapa Terraform Penting?
Jelaskan secara singkat:
- Manual klik-klik AWS Console rawan lupa dan tidak repeatable.
- Terraform membuat infrastructure menjadi code.
- Infrastructure bisa di-review seperti code.
- Cocok untuk provisioning AWS resource.
- Terraform membantu consistency antar environment dev/staging/prod.
- Terraform bukan pengganti AWS, tapi cara otomatis untuk membuat dan mengelola resource AWS.

Gunakan analogi:
- AWS Console = bikin rumah dengan klik manual.
- Terraform = blueprint rumah yang bisa dijalankan ulang.

2. Terraform Mental Model
Jelaskan flow:
Write .tf files -> terraform init -> terraform plan -> terraform apply -> infrastructure created -> state updated

Buat visual diagram HTML/CSS:
main.tf + variables.tf + outputs.tf
        ↓
terraform init
        ↓
terraform plan
        ↓
terraform apply
        ↓
AWS Resource
        ↓
terraform.tfstate

3. Instalasi dan Basic Setup
Bahas secara singkat:
- Install Terraform
- Cek versi:
terraform version
- Install AWS CLI
- Configure AWS CLI:
aws configure
- Cek identity:
aws sts get-caller-identity

Tambahkan warning:
- Jangan commit access key ke GitHub.
- Jangan taruh credential hardcoded di file .tf.
- Pakai IAM user/role dengan permission minimum.

4. Struktur File Terraform
Bahas:
- main.tf
- variables.tf
- outputs.tf
- provider.tf
- versions.tf
- terraform.tfvars
- .terraform.lock.hcl
- terraform.tfstate
- .gitignore

Buat contoh struktur folder:
terraform-aws-basic/
├── main.tf
├── provider.tf
├── variables.tf
├── outputs.tf
├── versions.tf
├── terraform.tfvars
└── .gitignore

Jelaskan fungsi masing-masing file secara compact.

5. Provider AWS
Bahas:
- Apa itu provider
- Kenapa Terraform butuh provider AWS
- required_providers
- provider "aws"
- region
- version constraint secara basic

Berikan contoh kode:
terraform {
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 6.0"
    }
  }
}

provider "aws" {
  region = var.aws_region
}

Catatan:
- Validasi versi AWS provider terbaru dari Terraform Registry.
- Jangan hardcode versi kalau tidak tervalidasi.
- Kalau versi terbaru berbeda, sesuaikan dengan dokumentasi terbaru.

6. Terraform Core Commands
Bahas command:
terraform init
terraform fmt
terraform validate
terraform plan
terraform apply
terraform destroy
terraform show
terraform state list
terraform output

Untuk setiap command, jelaskan:
- Fungsinya
- Kapan dipakai
- Contoh real kerjaan

Contoh:
terraform init
terraform fmt
terraform validate
terraform plan
terraform apply
terraform destroy

Tambahkan warning:
- Jangan asal terraform destroy.
- Selalu baca terraform plan sebelum apply.
- Jangan apply resource mahal tanpa sadar.

7. Resource dan Data Source
Bahas:
- resource = membuat/mengelola infrastructure
- data source = membaca resource existing
- Bedanya resource dan data source

Contoh:
resource "aws_instance" "web" {
  ami           = data.aws_ami.ubuntu.id
  instance_type = "t3.micro"
}

data "aws_ami" "ubuntu" {
  most_recent = true
  owners      = ["099720109477"]

  filter {
    name   = "name"
    values = ["ubuntu/images/hvm-ssd/ubuntu-*-amd64-server-*"]
  }
}

Catatan:
- Validasi data source dan argument via Terraform AWS Provider Registry.
- Jangan gunakan AMI hardcoded kalau bisa pakai data source.

8. Variable dan Output
Bahas:
- variable
- default value
- type
- description
- terraform.tfvars
- output

Contoh:
variable "aws_region" {
  description = "AWS region untuk deploy resource"
  type        = string
  default     = "ap-southeast-1"
}

variable "instance_type" {
  description = "EC2 instance type"
  type        = string
  default     = "t3.micro"
}

output "instance_public_ip" {
  value = aws_instance.web.public_ip
}

Real case:
“Supaya region dan instance type bisa diganti tanpa ubah main.tf.”

9. Terraform State
Bahas:
- Apa itu terraform.tfstate
- Kenapa state penting
- Terraform pakai state untuk tahu resource mana yang dia kelola
- Jangan edit state manual
- Jangan commit terraform.tfstate ke GitHub
- Bahaya state berisi informasi sensitif
- Local state vs remote state

Buat visual:
Terraform Code -> State -> Real AWS Resource

Common mistake:
- State hilang
- State di-commit ke GitHub
- Resource dibuat manual lalu Terraform tidak tahu
- Dua orang apply dari state lokal berbeda

10. Remote Backend Basic
Bahas:
- Kenapa butuh remote backend
- S3 backend untuk menyimpan state
- DynamoDB lock jika masih relevan dengan best practice terbaru, validasi dari docs
- State locking
- Team collaboration

Berikan contoh backend:
terraform {
  backend "s3" {
    bucket = "my-terraform-state-bucket"
    key    = "dev/terraform.tfstate"
    region = "ap-southeast-1"
  }
}

Catatan:
- Jelaskan bahwa bucket backend biasanya dibuat terlebih dahulu.
- Jangan terlalu dalam.
- Jangan membuat learner langsung deploy backend kompleks kalau belum paham basic.

11. Mini Lab 1: Deploy EC2 Ubuntu dengan Terraform
Tujuan:
Membuat EC2 sederhana menggunakan Terraform.

Resource:
- VPC default atau existing default VPC untuk pemula
- Security Group allow SSH dan HTTP
- EC2 Ubuntu
- User data install Nginx
- Output public IP

Kode harus dibuat modular tapi tetap simple.

Wajib ada:
provider.tf
variables.tf
main.tf
outputs.tf

Contoh high-level:
- Ambil AMI Ubuntu latest via data source
- Buat security group
- Buat EC2
- Install Nginx via user_data
- Output public IP

Security warning:
- SSH 0.0.0.0/0 tidak direkomendasikan untuk real production.
- Untuk lab boleh sementara, tapi jelaskan sebaiknya batasi ke IP sendiri.
- Jangan expose port yang tidak perlu.

12. Mini Lab 2: S3 Bucket Basic
Tujuan:
Membuat S3 bucket basic dengan security yang aman.

Bahas:
- Bucket name harus global unique
- Block Public Access
- Versioning optional
- Encryption
- Tagging

Kode contoh:
- aws_s3_bucket
- public access block
- versioning
- encryption jika sesuai resource terbaru AWS provider

Catatan:
- Validasi resource terbaru dari AWS provider docs.
- Jangan pakai resource/argument deprecated.

13. Mini Lab 3: VPC Super Basic
Tujuan:
Mengenalkan VPC custom secara sederhana.

Resource:
- VPC
- Public subnet
- Internet Gateway
- Route Table
- Route Table Association

Jangan buat NAT Gateway karena bisa mahal untuk pemula.
Jangan buat private subnet dulu kecuali hanya visual/concept.

Tekankan:
- NAT Gateway bisa menambah biaya.
- Untuk lab basic, cukup public subnet dulu.

14. Mini Project Akhir
Judul:
“Deploy Static Web Server AWS dengan Terraform”

Arsitektur:
User -> Internet -> Security Group -> EC2 Ubuntu + Nginx

Optional:
- S3 bucket untuk artifact/static asset
- CloudWatch basic concept, tidak perlu implement panjang

Step:
1. Setup AWS CLI
2. Buat folder project Terraform
3. Tulis provider.tf
4. Tulis variables.tf
5. Tulis main.tf
6. Tulis outputs.tf
7. Jalankan terraform init
8. Jalankan terraform fmt
9. Jalankan terraform validate
10. Jalankan terraform plan
11. Jalankan terraform apply
12. Ambil output public IP
13. Test website via browser/curl
14. Cek resource di AWS Console
15. Jalankan terraform destroy setelah lab selesai

15. Best Practice DevOps
Bahas:
- Selalu pakai terraform fmt
- Selalu terraform validate
- Selalu review terraform plan
- Jangan commit tfstate
- Jangan hardcode secret
- Pakai variable
- Pakai output seperlunya
- Pakai naming convention
- Pakai tag
- Pisahkan environment dev/staging/prod
- Pakai remote backend untuk team
- Batasi IAM permission
- Gunakan .gitignore
- Hati-hati resource berbayar

16. .gitignore Terraform
Berikan contoh:
.terraform/
*.tfstate
*.tfstate.*
*.tfvars
crash.log
crash.*.log
override.tf
override.tf.json
*_override.tf
*_override.tf.json
.terraform.lock.hcl optional jelaskan biasanya boleh di-commit untuk dependency lock consistency

Jelaskan singkat:
- Kenapa tfstate jangan di-commit
- Kenapa tfvars bisa berisi secret
- Kenapa .terraform folder jangan di-commit

17. Troubleshooting Terraform
Buat visual flowchart:
Terraform error?
1. terraform fmt
2. terraform validate
3. cek provider version
4. cek AWS credential
5. aws sts get-caller-identity
6. cek IAM permission
7. cek region
8. cek resource sudah ada atau conflict
9. cek state
10. baca error message pelan-pelan

Bahas error umum:
- No valid credential sources found
- AccessDenied
- InvalidAMIID.NotFound
- Resource already exists
- Dependency error
- Error karena region salah
- Error karena quota/limit

18. Cheatsheet Terraform
Buat tabel:
Kategori | Command / Konsep | Fungsi | Contoh

Isi:
- init
- fmt
- validate
- plan
- apply
- destroy
- output
- state list
- variable
- output
- provider
- resource
- data source
- backend
- module

19. Module Basic
Bahas compact:
- Module = reusable Terraform configuration
- Root module
- Child module
- Kapan butuh module
- Jangan buru-buru bikin module kalau basic belum kuat

Contoh struktur:
modules/
└── ec2-web/
    ├── main.tf
    ├── variables.tf
    └── outputs.tf

Environments:
envs/
├── dev/
└── prod/

Jelaskan singkat:
- Module dipakai agar kode tidak copy-paste.
- Tapi untuk pemula, pahami resource dulu sebelum module.

20. Quiz Interaktif
Buat 15 pertanyaan:
Contoh:
- Command pertama yang dijalankan di project Terraform?
- Command untuk melihat rencana perubahan?
- Kenapa terraform.tfstate tidak boleh di-commit?
- Apa fungsi provider?
- Apa beda resource dan data source?
- Apa fungsi output?
- Apa fungsi variable?
- Apa command untuk format file Terraform?
- Apa command untuk validasi syntax?
- Kenapa harus baca plan sebelum apply?
- Apa itu remote backend?
- Kenapa jangan hardcode secret?
- Apa fungsi user_data di EC2?
- Apa risiko terraform destroy?
- Kenapa NAT Gateway perlu hati-hati untuk lab pemula?

FITUR INTERAKTIF HTML:
- Sidebar/table of contents.
- Progress bar.
- Card per module.
- Accordion per topic.
- Command block dengan tombol copy.
- Mini terminal simulator:
  - terraform init
  - terraform plan
  - terraform apply
  - terraform destroy
- Quiz interaktif dengan skor.
- Visual diagram Terraform workflow.
- Visual diagram Terraform state.
- Visual warning untuk dangerous command.
- Smooth scroll.
- Reveal animation saat card masuk viewport.
- Responsive mobile.

TONE:
- Casual tapi profesional.
- Seperti mentor DevOps ngajarin langsung.
- Jangan terlalu akademis.
- Jangan terlalu panjang.
- Fokus ke real case.
- Setiap section harus punya:
  1. Penjelasan singkat
  2. Kenapa penting di real kerjaan
  3. Command atau contoh kode
  4. Common mistake
  5. Mini practice

VALIDASI DOKUMENTASI:
Sebelum generate HTML:
1. Validasi konsep Terraform dari official HashiCorp Terraform Docs:
   - Terraform CLI commands
   - Providers
   - State
   - Variables
   - Outputs
   - Modules
   - Backend
2. Validasi AWS provider dari Terraform Registry:
   - hashicorp/aws provider
   - aws_instance
   - aws_security_group
   - aws_s3_bucket
   - aws_s3_bucket_public_access_block
   - aws_vpc
   - aws_subnet
   - aws_internet_gateway
   - aws_route_table
3. Validasi AWS service concept via AWS MCP Server:
   - EC2
   - Security Group
   - S3 security
   - VPC
   - IAM least privilege
   - Billing/cost cleanup warning

Di bagian bawah HTML, tambahkan section kecil:
“Materi ini disusun berdasarkan validasi HashiCorp Terraform Documentation, Terraform Registry AWS Provider, dan AWS Documentation via AWS MCP Server pada saat pembuatan.”

Jangan mencantumkan klaim harga, free tier, atau limit pasti kecuali sudah divalidasi dari dokumentasi/pricing terbaru.
Untuk biaya, cukup beri warning general:
- EC2 running bisa kena biaya
- EBS volume bisa kena biaya
- NAT Gateway bisa mahal untuk lab
- Load Balancer bisa kena biaya
- Public IPv4 bisa memiliki biaya tergantung kondisi AWS terbaru
- Selalu cleanup resource setelah lab

OUTPUT AKHIR:
Berikan hanya kode HTML lengkap dari <!DOCTYPE html> sampai </html>.
Jangan ada markdown.
Jangan ada penjelasan tambahan di luar kode.