function iniciar(){
    let links=[
        "https://victorxx.github.io/vpsvendarandom01/",
        "https://victorxx.github.io/erpgithubrnadom01/",
        "https://victorxx.github.io/laudobancariogithub/",
        "https://victorxx.github.io/VPSVENDA/contatoroberto.html",
        "https://victorxx.github.io/reflexao01git/",
        "https://victorxx.github.io/redirecionadorlinksgit1/",
        "https://victorxx.github.io/airbnbrandom01/",
        "https://www.larissasaib.com.br/larissa-saib",
        "https://laudobancriotimline.netlify.app/",
        "https://victorxx.github.io/laudobancariogithub/",
        "https://victorxx.github.io/VPSVENDA/contatoroberto.html",
        "https://geocredibnkvitoria.com/",
        "https://victorxx.github.io/topicogithub01/",
        "https://victorxx.github.io/topicogithub01/randomizador.html",
        "https://victorxx.github.io/redirecionadorlinksgit1/",
        "https://victorxx.github.io/carros01gith/uteis.html",
        "https://victorxx.github.io/videosgihb01/"

      ];
      const mudar=links[Math.floor(Math.random()* links.length)];
      document.getElementById('novo').href=mudar;

}
setInterval(iniciar,900);
