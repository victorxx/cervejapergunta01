document.getElementById('btn').onclick = function () {
  const pergunta = prompt('Digite uma dúvida sobre cerveja');

  if (!pergunta) {
    alert('Você precisa digitar algo.');
    return;
  }

  // Função para normalizar (remover acentos e deixar minúsculo)
  function normalizar(texto) {
    return texto
      .toLowerCase()
      .normalize("NFD")
      .replace(/[\u0300-\u036f]/g, "");
  }

  const texto = normalizar(pergunta);

  // Respostas baseadas em palavras-chave
  const respostas = [
    {
      palavras: ['sem alcool', 'sem álcool'],
      conteudo: `
        <iframe width="560" height="315" src="https://www.youtube.com/embed/E9vOhi_BXnw?si=kDshrdki11rJloBY"
          title="Cerveja sem álcool" frameborder="0" allow="accelerometer; autoplay; clipboard-write;
          encrypted-media; gyroscope; picture-in-picture; web-share"
          referrerpolicy="strict-origin-when-cross-origin" allowfullscreen>
        </iframe>
      `
    },
    {
      palavras: ['malte', 'cerveja de malte'],
      conteudo: `
        <iframe width="560" height="315" src="https://www.youtube.com/embed/60pLRiZgnK8?si=o_WcGKKfHSbmR0ZO" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
    `
    },
    
    
  ];

  // Procurar a primeira resposta correspondente
  let respostaEncontrada = null;

  for (let item of respostas) {
    const encontrou = item.palavras.some(palavra => texto.includes(normalizar(palavra)));
    if (encontrou) {
      respostaEncontrada = item.conteudo;
      break;
    }
  }

  // Mostrar resultado
  const saida = document.getElementById('saida');
  if (respostaEncontrada) {
    saida.innerHTML = respostaEncontrada;
  } else {
    saida.innerText = 'Nenhum conteúdo correspondente encontrado.';
  }
};
