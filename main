import requests

def get_http_data(host: str):
    try:
        # Corrige a barra invertida se necessário
        url = host.replace("\\", "/")
        
        response = requests.get(url)

        data = {
            'headers': dict(response.headers),
            'content': response.text,
            'cookies': response.cookies.get_dict()
        }

        return data

    except requests.RequestException as e:
        return {'error': str(e)}

if __name__ == '__main__':
    endpoint = 'ultimas'
    host = 'https://httpbin.org/get'

    dados = get_http_data(host)

    if 'error' in dados:
        print("Erro:", dados['error'])
    else:
        print("Headers:", dados['headers'])
        print("Cookies:", dados['cookies'])
        print("Conteúdo (resumo):", dados['content'][:500])  # imprime só o começo do HTML
