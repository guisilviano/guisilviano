# Função de busca binária
def binary_search(arr, target):
    low = 0
    high = len(arr) - 1
    
    while low <= high:
        mid = (low + high) // 2  # Calcula o índice do meio da lista
        
        # Verifica se o elemento está no meio
        if arr[mid] == target:
            return mid  # Elemento encontrado, retorna o índice
        
        # Se o alvo for menor que o valor no meio, ignora a metade superior
        elif arr[mid] > target:
            high = mid - 1
        
        # Caso contrário, ignora a metade inferior
        else:
            low = mid + 1
    
    return -1  # Elemento não encontrado

# Testes da função
def test_binary_search():
    # Exemplo de lista ordenada
    arr = [1, 3, 5, 7, 9, 11, 13, 15, 17]
    target = 7
    
    result = binary_search(arr, target)
    
    if result != -1:
        print(f"Elemento {target} encontrado no índice {result}.")
    else:
        print(f"Elemento {target} não encontrado.")

    # Testando um elemento ausente
    target = 10
    result = binary_search(arr, target)
    if result != -1:
        print(f"Elemento {target} encontrado no índice {result}.")
    else:
        print(f"Elemento {target} não encontrado.")

# Chama a função de teste
test_binary_search()
