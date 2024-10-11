## 1.1 Instalación de zonas mestras primarias - Alejandro Rey Otero

---

**1**. Instala o servidor BIND9 no equipo darthvader. Comproba que xa funciona coma servidor DNS caché pegando no documento de entrega a saída deste comando dig @localhost www.edu.xunta.es

- Resultado do comando `dig @localhost www.edu.xunta.es` 

  ![Imagen Ejer1_1.png](/imagenes/Ejer1_1.png)

---

**2**. Configura o servidor BIND9 para que empregue como reenviador 8.8.8.8. pegando no documento de entrega contido do ficheiro "/etc/bind/named.conf.options" e a saída deste comando: dig @localhost www.mecd.gob.es

- Resultado do documento **/etc/bind/named.conf.options**

  ![Imagen Ejer2_1.png](/imagenes/Ejer2_1.png)

- Resultado do comando `dig @localhost www.mecd.gob.es`

  ![Imagen Ejer2_2.png](/imagenes/Ejer2_2.png)

---

**3**. Instala unha zona primaria de resolución directa chamada "starwars.lan" e engade os seguintes rexistros de recursos (a maiores dos rexistros NS e SOA imprescindibles):
Tipo A: darthvader con IP 192.168.20.10
Tipo A: skywalker con IP 192.168.20.101
Tipo A: skywalker con IP 192.168.20.111
Tipo A: luke con IP 192.168.20.22
Tipo A: darthsidious con IP 192.168.20.11
Tipo A: yoda con IP 192.168.20.24 e 192.168.20.25
Tipo A: c3p0 con IP 192.168.20.26
Tipo CNAME palpatine a darthsidious
TIPO MX con prioridade 10 sobre o equipo c3po
TIPO TXT "lenda" con "Que a forza te acompanhe"
TIPO NS con darthsidious
Pega no documento de entrega o contido do arquivo de zona, e do arquivo /etc/bind/named.conf.local

- Resultado do documento **/etc/bind/db.starwars.lan**

  ![Imagen Ejer3_1.png](/imagenes/Ejer3_1.png)

- Resultado do documento **/etc/bind/named.conf.local**

  ![Imagen Ejer3_2.png](/imagenes/Ejer3_2.png)

---

**4**. Instala unha zona de resolución inversa que teña que ver co enderezo do equipo darthvader, e engade rexistros PTR para os rexistros tipo A do exercicio anterior. Pega no documento de entrega o contido do arquivo de zona, e do arquivo /etc/bind/named.conf.local

- Resultado do documento **/etc/bind/db.20.168.192**

  ![Imagen Ejer4_1.png](/imagenes/Ejer4_1.png)

- Resultado do documento **/etc/bind/named.conf.local**

  ![Imagen Ejer4_2.png](/imagenes/Ejer4_2.png)

---

**5**. Comproba que podes resolver os distintos rexistros de recursos. Pega no documento de entrega a saída dos comandos:
nslookup darthvader.starwars.lan localhost
nslookup skywalker.starwars.lan localhost
nslookup starwars.lan localhost
nslookup -q=mx starwars.lan localhost
nslookup -q=ns starwars.lan localhost
nslookup -q=soa starwars.lan localhost
nslookup -q=txt lenda.starwars.lan localhost
nslookup 192.168.20.11 localhost

- Resultado do comando `nslookup darthvader.starwars.lan`

  ![Imagen Ejer5_1.png](/imagenes/Ejer5_1.png)

- Resultado do comando `nslookup skywalker.starwars.lan`

  ![Imagen Ejer5_2.png](/imagenes/Ejer5_2.png)

- Resultado do comando `nslookup starwars.lan`

  ![Imagen Ejer5_3.png](/imagenes/Ejer5_3.png)

- Resultado do comando `nslookup -q=mx starwars.lan`

  ![Imagen Ejer5_4.png](/imagenes/Ejer5_4.png)

- Resultado do comando `nslookup -q=ns starwars.lan`

  ![Imagen Ejer5_5.png](/imagenes/Ejer5_5.png)

- Resultado do comando `nslookup -q=soa starwars.lan`

  ![Imagen Ejer5_6.png](/imagenes/Ejer5_6.png)

- Resultado do comando `nslookup -q=txt lenda.starwars.lan`

  ![Imagen Ejer5_7.png](/imagenes/Ejer5_7.png)

- Resultado do comando `nslookup 192.168.20.11`

  ![Imagen Ejer5_8.png](/imagenes/Ejer5_8.png)

---

