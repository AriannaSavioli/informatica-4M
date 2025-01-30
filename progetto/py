#Savioli Arianna 4M
#Progetto sulla programmazione ad oggetti
#il codice simula un negozio online di trucchi

#creazione della classe prodotto
class Prodotto:
    #dichiarazione degli attributi
    def __init__(self, nome, prezzo, disponibilita):
        self.nome = nome
        self.prezzo = prezzo
        self.disponibilita = disponibilita

#creazione della classe produttore
class Produttore:
    #dichiarazione degli attributi
    def __init__(self, nome):
        self.nome = nome
        self.prodotti = []  #la lista contiene i prodotti che questo produttore ha prodotto
    #aggiunta di un prodotto alla lista dei prodotti creati da questo produttore
    def produce(self, prodotto):
        self.prodotti.append(prodotto)  

#creazione della classe categoria
class Categoria:
    #dichiarazione degli attributi
    def __init__(self, nome):
        self.nome = nome
        self.prodotti = []  #la lista contiene i prodotti appartenenti a questa categoria
    #aggiunta di un prodotto alla lista dei prodotti appartenenti a questa categoria
    def aggiungiProdotto(self, prodotto):
        self.prodotti.append(prodotto) 

#creazione della classe categoria premium che eredita da categoria
class CategoriaPremium(Categoria):
    #questa classe non aggiunge nulla alla classe categoria
    pass 

#creazione della classe utente
class Utente:
    #dichiarazione degli attributi
    def __init__(self, nome, indirizzo):
        self.nome = nome
        self.indirizzo = indirizzo
        self.carrello = []  #lista dei prodotti contenuti nel carrello dell'utente
        self.ordini = []  #lista degli ordini effettuati dall'utente
    #aggiunta di un prodotto al carrello dell'utente
    def aggiungiAlCarrello(self, prodotto):
        self.carrello.append(prodotto)  
    #metodo che permette di gestire gli ordini
    def effettuaOrdine(self):
        ordine = Ordine(self, self.carrello)  #creazione di un nuovo ordine
        self.ordini.append(ordine)  #aggiunta dell'ordine alla lista degli ordini dell'utente
        self.carrello = []  #svuotamento del carrello a fine ordine
        return ordine

#creazione della classe ordine
class Ordine:
    #dichiarazione degli attributi
    def __init__(self, utente, carrello):
        self.utente = utente
        self.prodottiAcquistati = carrello  #lista dei prodotti acquistati in questo ordine
        self.stato = "In elaborazione..."  #stato iniziale dell'ordine
    #metodo che permette di cambiare lo stato dell'ordine una volta che viene spedito
    def spedisceOrdine(self):
        self.stato = "Spedito!"

#esempio di utilizzo delle classi
prodotto1 = Prodotto("Mascara", 15.99, 100)
prodotto2 = Prodotto("Illuminante", 17.49, 40)
produttore1 = Produttore("Maybelline")
produttore2 = Produttore("kiko")
produttore1.produce(prodotto1)
produttore2.produce(prodotto2)
categoria1 = Categoria("Trucco occhi")
categoria1.aggiungiProdotto(prodotto1)
categoriaPremium1 = CategoriaPremium("Trucco viso")
categoriaPremium1.aggiungiProdotto(prodotto2)
utente1 = Utente("Rebecca", "Via Italia 123")
utente1.aggiungiAlCarrello(prodotto1)
utente1.aggiungiAlCarrello(prodotto2)
ordine1 = utente1.effettuaOrdine()
ordine1.spedisceOrdine()
#stampa di alcune informazioni 
print("Prodotto 1:", prodotto1.nome)
print("Prodotto 2:", prodotto2.nome)
print("Utente 1:", utente1.nome)
print("Ordine 1 - Stato:", ordine1.stato)
print("Ordine 1 - Prodotti Acquistati:", [prodotto.nome for prodotto in ordine1.prodottiAcquistati])
