	package main

	import (
		"fmt"
		"log"
		"net/http"
	)

	func main () {  

		http.HandleFunc("/", homeHandler)
		fmt.Println("Сервер запущен: http://localhost:8080")
	
		err := http.ListenAndServe("127.0.0.1:8080", nil)

		if err != nil { 
			log.Fatal(err)
		}
	}

	func homeHandler(w http.ResponseWriter, r *http.Request) {
		fmt.Fprintln(w, "Oh my God! Это мой первый веб-сервер на Go!? Какая прелесть!")
	}
