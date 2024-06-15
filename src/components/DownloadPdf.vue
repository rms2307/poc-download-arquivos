<template>
    <div>
      <button @click="downloadPdf">Download PDF</button>
    </div>
  </template>
  
  <script>
  import axios from 'axios';
  
  export default {
    name: 'DownloadPdf',
    methods: {
      async downloadPdf() {
        try {
          const response = await axios.get('https://localhost:7105/Base64ToFile', {
            responseType: 'blob'
          });
          
          const url = window.URL.createObjectURL(new Blob([response.data]));
          const link = document.createElement('a');
          link.href = url;
          link.setAttribute('download', 'arquivo-de-teste.pdf');
          document.body.appendChild(link);
          link.click();
          link.remove();
        } catch (error) {
          console.error('Erro ao baixar o PDF:', error);
        }
      }
    }
  }
  </script>
  
  <style scoped>
  button {
    padding: 10px 20px;
    font-size: 16px;
    background-color: #42b983;
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
  }
  </style>
  