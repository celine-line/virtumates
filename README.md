addEventListener('fetch', event => {
  event.respondWith(handleRequest(event.request))
}

async function handleRequest(request) {
  const { pathname } = new URL(request.url)
  return fetch(`https://www.instagram.com${pathname}?__a=1`, {
    headers: { 'User-Agent': 'Mozilla/5.0' }
  })
}
