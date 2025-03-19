addEventListener('fetch', event => {
    event.respondWith(handleRequest(event.request))
  })
  
  async function handleRequest(request) {
    // URL gốc của Google Apps Script Web App (thay bằng URL thật của bạn)
    const scriptURL = "https://script.google.com/a/macros/weldcom.vn/s/AKfycbxKZwP-x1zI4CDakeZrvYK79wMoj-FKbQXL4XA2LVROUm56wZB_3sYdVW7ITWEXW626/exec"
    
    // Nối query string nếu có
    const url = new URL(request.url)
    const targetUrl = scriptURL + url.search
    
    const response = await fetch(targetUrl, {
      method: request.method,
      headers: request.headers,
      body: request.method === "GET" || request.method === "HEAD" ? null : request.body,
    })
    
    return new Response(response.body, {
      status: response.status,
      statusText: response.statusText,
      headers: response.headers
    })
  }
