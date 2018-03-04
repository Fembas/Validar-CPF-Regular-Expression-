 Validar-CPF-Regular-Expression
Atividade professor Thales#!/bin/bash

#................................................................................Data: 04/03/2018                        
#................................................................................Wilson                               
#................................................................................Obrigado Teacher pela oportunidade    
	
	
NOME(){
	read -p "Digite o seu nome. Vai logo...: " nome	
	echo $nome | grep -E '^[0-9.-\=_,><?:;!@#$%¨&*()_+\""][ ]$'
	if [ $? == 1 ]; then
		clear
		echo "Opa, deu válido!"
		sleep 1
		clear
		EMAIl
	else
		echo "Vish... Inválido. Que enganar quem?..."
		echo "Digite novamente, Pexte:"
		sleep 1
		clear
		NOME
	fi
}

EMAIL(){
	read -p "Digite o seu email. Vai logo...: " email	
	echo $email | grep -E '^(A-Za-z0-9\.\_\-)+[@][A-Za-z0-9]+(\.com|\.br)|(\.com\.br)$'
	if [ $? == 1 ]; then
		clear
		echo "Opa, deu válido!"
		sleep 1
		clear
		TELEFONE
	else
		echo "Vish... Inválido!"
		echo "Digite novamente, Pexte:"
		sleep 1
		clear
		EMAIL
	fi
}

TELEFONE(){
	echo "Formato do telefone: (XX)XXXX-XXXX"
	read -p "Digite o seu telefone. Vai logo...: " telefone	
	echo $telefone | grep -E '^[(][0-9]{2}[)][0-9]{4}+-[0-9]{4}$'
	if [ $? == 0 ]; then
		clear
		echo "Opa, deu válido, Continue assim...!"
		sleep 3
		clear
		RG
	else
		echo "Vish... Inválido!"
		echo "Digite novamente, Pexte:"
		sleep 3
		clear
		TELEFONE
	fi
}


RG(){
	echo "Formato do documento: XX.XXX.XXX-X"
	read -p "Digite o seu rg... Demora da Porra: " rg	
	echo $rg | grep -E '^[(][0-9]{2}[)][0-9]{4}+-[0-9]{4}$'
	if [ $? == 0 ]; then
		clear
		echo "Bom, deu válido!"
		sleep 3
		clear
		CPF
	else
		echo "Vish... Inválido!"
		echo "Digite novamente, Seu Pereba:"
		sleep 3
		clear
		RG
	fi
}

CPF(){
	echo "Formato do documento: XXX.XXX.XXX-XX"
	read -p "Digite o seu cpf. Vai logo... " cpf	
	echo $cpf | grep -E '^[0-9]{3}[.][0-9]{3}[.][0-9]{3}[-][0-9]{2}$'
	if [ $? == 0 ]; then
		clear
		echo "Opa, deu válido!"
		sleep 2
		clear
		NASC
	else
		echo "Vish... Inválido!"
		echo "Digite novamente, Pexte:"
		sleep 2
		clear
		CPF
	fi
}

NASC(){
	echo "Formato da data: XX/XX/XXXX"
	read -p "Digite a data de seu nascimento... Se é que sabe: " nasc	
	echo $nasc | grep -E '^[0-9]{2}\/[0-9]{2}\/[0-9]{4}$'
	if [ $? == 0 ]; then
		clear
		echo "Opa, deu válido!"
		sleep 2
		clear
		NASC
	else
		echo "Vish... Inválido, (((Mano do Céu...)))!"
		echo "Digite novamente, Pexte:"
		sleep 2
		clear
		CPF
	fi
}

IP(){
        read -p "Digite o seu ip  ((Introspecção Interna...)) " ip
        		
		echo $ip | grep -E '^([0-9]|[1-9][0-9]|1[0-9]{2}|2[0-4][0-9]|25[0-5])(\.([0-9]|[1-9][0-9]|1[0-9]{2}|2[0-4][0-9]|25[0-5])){3}$'
		
		if [ $? == 0 ]; then
		clear
		echo "Opa, deu válido!"
		sleep 2
		clear
		MASK
	else
		echo "Vish... Inválido!"
		echo "Digite novamente, Pexte:"
		sleep 2
		clear
		IP
	fi
    }

MASK(){
        read -p "Digite a sua máscara de rede: Da Rede, não a sua... " mask
        		
		echo $mask | grep -E '^([0-9]|[1-9][0-9]|1[0-9]{2}|2[0-4][0-9]|25[0-5])(\.([0-9]|[1-9][0-9]|1[0-9]{2}|2[0-4][0-9]|25[0-5])){3}$'
		
		if [ $? == 0 ]; then
		clear
		echo "Opa, deu válido!"
		echo " Cadastro Sucesso...Milagre da PORRA!"
		sleep 2
		clear
		
	else
		echo "Aff... Inválido. No Ultimo vai fazer errado?"
		echo "Digite novamente, Verme..."
		sleep 2
		clear
		MASK
	fi
  
}
NOME
