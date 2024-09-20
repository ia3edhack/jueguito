tipo JargoWord = {
  original: cadena;
  traducción: cadena;
};

constante jargoWords: JargoWord[] = [
  { original: "fregado", traducción: "estruviar" },
  { original: "trol", traducción: "engendrador" },
  { original: "pwned", traducción: "derrotado" },
  { original: "novato", traducción: "novato" },
  { original: "hax", traducción: "trampa" },
];

función traducir(palabra: cadena): cadena | null {
  const jargoWord = jargoWords.find((w) => w.original.toLowerCase() === palabra.toLowerCase());
  devolver jargoWord ? jargoWord.translation : null;
}

función jargo(entrada: cadena): cadena {
  const palabras = entrada.split(" ");
  dejar traducido = "";

  para (const palabra de palabras) {
    const traducción = traducir(palabra);
    si (traducción) {
      traducido += traducción + " ";
    } demás {
      traducido += palabra + " ";
    }
  }

  devuelve traducido.trim();
}

// Ejemplo de uso
console.log(jargo("Estoy fregado, novato.")); // Salida: "Estruviate, engendrador."
console.log(jargo("Mi PC fue pwned.")); // Salida: "Mi PC fue derrotado".
