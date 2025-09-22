````markdown
# DevOps Playground 🚀
````
Repositório focado em **projetos DevOps**, com ênfase em práticas de automação, administração de servidores e boas práticas para ambientes Linux.

---

## 📌 Sobre DevOps
DevOps é uma abordagem cultural e técnica que integra equipes de **desenvolvimento** e **operações**, com o objetivo de entregar software de forma mais rápida, confiável e segura.  
Seus pilares incluem:
- **Automação** de processos repetitivos e críticos;
- **Integração contínua (CI)** e **entrega contínua (CD)** para acelerar ciclos de desenvolvimento;
- **Monitoramento proativo** para prevenir incidentes;
- **Colaboração e comunicação** entre áreas tradicionalmente separadas.

O resultado é um fluxo mais eficiente, com menos falhas e maior capacidade de escalar sistemas de maneira previsível.

---

## 👨‍💻 Autor
- Caio Silveira ([Caiorem](https://github.com/Caiorem))
- [LinkedIn](https://linkedin.com/in/caiorem)

---

## 🔧 Guia rápido Linux (RHEL e derivados)

### Estrutura básica
- Tudo é arquivo (inclusive diretórios, processos e dispositivos).
- `.` → diretório atual  
- `..` → diretório pai  
- `$` → usuário comum  
- `#` → root  

---

### Diretórios essenciais do GNU/Linux
- `/etc` → Arquivos de configuração do sistema e serviços.  
- `/var` → Dados variáveis (logs, cache, fila de impressão, pacotes).  
- `/bin` → Binários essenciais para todos os usuários.  
- `/sbin` → Binários administrativos (normalmente apenas root).  
- `/usr` → Programas, bibliotecas e documentação adicionais.  
- `/home` → Diretórios pessoais dos usuários.  
- `/root` → Diretório pessoal do superusuário.  
- `/tmp` → Arquivos temporários.  
- `/boot` → Arquivos de inicialização (kernel, bootloader).  
- `/dev` → Arquivos de dispositivos.  
- `/proc` → Informações do kernel e processos em tempo real.  
- `/mnt` e `/media` → Pontos de montagem de sistemas de arquivos.  

---

### Permissões de arquivos
No Linux, permissões são representadas por **valores numéricos (binários)**:

- `4` = leitura (**r**)  
- `2` = escrita (**w**)  
- `1` = execução (**x**)  

Exemplo de uso:
```bash
chmod 755 script.sh  # dono rwx, grupo r-x, outros r-x
````

---

### Gestão de processos e sistema

```bash
ps aux || ps -ef      # lista todos processos
top                   # monitor de processos
htop                  # versão melhorada do top
kill 1234             # mata processo pelo PID
df -h                 # uso de disco
free -h               # uso de memória
uname -a              # informações do kernel
cat /etc/os-release   # versão da distro
```

---

### Redes

```bash
hostname -I     # IPs da máquina
ping google.com # testa conectividade
ss -tulpn       # portas em uso
traceroute site # rota até um host
```

---

### Gestão de armazenamento (fstab e discos)

* O arquivo **`/etc/fstab`** define sistemas de arquivos que devem ser montados automaticamente na inicialização.

Exemplo de entrada:

```
UUID=xxxx-xxxx   /mnt/data   ext4   defaults   0   2
```

**Principais comandos:**

```bash
lsblk              # lista discos e partições
fdisk -l           # mostra discos disponíveis
mount /dev/sdX /mnt/pasta   # monta dispositivo
umount /mnt/pasta           # desmonta dispositivo
cat /etc/fstab     # mostra configurações persistentes
mount -a           # monta tudo que está no fstab
df -Th             # mostra uso dos sistemas de arquivos montados
```

---

### Usuários

```bash
whoami                  # usuário logado
sudo adduser novo       # cria usuário
sudo usermod -aG sudo x # adiciona ao grupo sudo
sudo deluser x --remove-home  # remove usuário + home
```
---

### Pacotes (RHEL)

```bash
sudo yum update         # atualiza pacotes
sudo yum install nginx  # instala pacote
sudo yum remove nginx   # remove pacote
```

---

## 📚 Referências úteis

* [Guia Foca](https://www.guiafoca.org/)
* [TabNews - lista de comandos básicos Linux](https://www.tabnews.com.br/AlexCampo/lista-de-comandos-mais-usados-no-linux)

---

## ⚠️ Nota final

Use este repositório como seu cinto de utilidades **DevOps**.
Mas lembre-se: com **rm -rf** vem grande responsabilidade.
