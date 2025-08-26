# JT Sistemas - Sistema de Gestão Empresarial

![Python](https://img.shields.io/badge/python-3.8+-blue.svg)
![Django](https://img.shields.io/badge/Django-4.2+-green.svg)
![Bootstrap](https://img.shields.io/badge/Bootstrap-5.3-purple.svg)
![License](https://img.shields.io/badge/license-MIT-blue.svg)

## 🚀 Visão Geral

O **JT Sistemas** é uma plataforma completa de gestão empresarial desenvolvida em Django, projetada para oferecer uma experiência moderna e intuitiva no gerenciamento de negócios. O sistema combina funcionalidades robustas com uma interface elegante e responsiva, proporcionando controle total sobre usuários, funcionários, clientes, serviços e agendamentos.

### ✨ Proposta do Sistema

O JT Sistemas foi concebido para ser a solução definitiva para empresas que buscam:

- **Gestão Centralizada**: Controle total de usuários, funcionários e clientes em uma única plataforma
- **Sistema de Agendamentos**: Funcionalidade completa para agendamento de serviços com controle de status
- **Relatórios Inteligentes**: Dashboard com métricas e relatórios detalhados para tomada de decisões
- **Integração WhatsApp**: Bot automatizado para atendimento e agendamentos via WhatsApp
- **Interface Moderna**: Design profissional com animações fluidas e experiência de usuário premium
- **Segurança Avançada**: Sistema de permissões granulares e auditoria completa

## 🎨 Sistema de Design e Paleta de Cores

### Paleta de Cores Principal

```css
/* Cores Primárias */
--primary-color: #2563eb        /* Azul Primário - Elementos principais */
--primary-dark: #1d4ed8         /* Azul Escuro - Estados hover/active */
--primary-light: #3b82f6        /* Azul Claro - Elementos secundários */

/* Cores Funcionais */
--success-color: #059669        /* Verde - Sucesso/Confirmações */
--success-light: #10b981        /* Verde Claro - Estados de sucesso */
--danger-color: #dc2626         /* Vermelho - Erros/Exclusões */
--danger-light: #ef4444         /* Vermelho Claro - Estados de alerta */
--warning-color: #d97706        /* Laranja - Avisos */
--info-color: #0891b2          /* Azul Info - Informações */

/* Tons Neutros */
--gray-50: #f8fafc             /* Fundo claro */
--gray-100: #f1f5f9            /* Fundo secundário */
--gray-200: #e2e8f0            /* Bordas sutis */
--gray-300: #cbd5e1            /* Bordas padrão */
--gray-400: #94a3b8            /* Texto secundário */
--gray-500: #64748b            /* Texto padrão */
--gray-600: #475569            /* Texto escuro */
--gray-700: #334155            /* Texto principal */
--gray-800: #1e293b            /* Texto destaque */
--gray-900: #0f172a            /* Texto máximo contraste */
```

### Gradientes e Efeitos

- **Fundo Principal**: Gradiente diagonal do cinza-50 ao cinza-100
- **Login**: Gradiente diagonal do roxo ao azul (#667eea → #764ba2)
- **Sidebar**: Gradiente vertical do azul escuro (#2c3e50 → #34495e)
- **Cards**: Sombras suaves com elevação progressiva no hover

## 🎯 Barra Lateral Interativa

### Características Principais

A barra lateral é o coração da navegação do sistema, oferecendo uma experiência fluida e intuitiva:

#### 📐 Dimensões e Layout
- **Largura Colapsada**: 70px (modo compacto)
- **Largura Expandida**: 280px (modo completo)
- **Altura**: 100vh (tela completa)
- **Posição**: Fixa à esquerda

#### 🎭 Estados e Comportamentos

1. **Estado Colapsado (Padrão)**
   - Mostra apenas ícones
   - Textos ocultos com `opacity: 0`
   - Largura de 70px

2. **Estado Expandido (Hover/Click)**
   - Exibe textos e ícones completos
   - Transição suave de 0.3s
   - Largura de 280px

3. **Estado Mobile**
   - Overlay completo na tela
   - Fundo semitransparente
   - Slide-in animation

#### ⚡ Animações Detalhadas

##### Expansão da Sidebar
```css
.sidebar {
    width: 70px;
    transition: all 0.3s ease;
}

.sidebar:hover,
.sidebar.expanded {
    width: 280px;
}
```

##### Fade-in dos Textos
```css
.nav-text {
    opacity: 0;
    transition: opacity 0.3s ease;
    white-space: nowrap;
}

.sidebar:hover .nav-text,
.sidebar.expanded .nav-text {
    opacity: 1;
}
```

##### Rotação dos Ícones de Dropdown
```css
.dropdown .nav-link::after {
    content: '\f078'; /* FontAwesome chevron-down */
    transition: transform 0.3s ease;
}

.dropdown .nav-link[aria-expanded="true"]::after {
    transform: rotate(180deg);
}
```

##### Hover Effects nos Links
```css
.nav-link:hover {
    background: rgba(108, 117, 125, 0.25);
    color: #ffffff;
    transform: translateX(2px); /* Deslizamento sutil */
}
```

#### 🎮 Interações JavaScript

O sistema de sidebar utiliza uma classe JavaScript dedicada (`SidebarManager`) que gerencia:

1. **Detecção de Dispositivo**: Diferencia comportamento mobile/desktop
2. **Hover Management**: Controla expansão/colapso com delays
3. **Dropdown Control**: Gerencia abertura/fechamento de submenus
4. **Active State**: Destaca página atual automaticamente
5. **Responsive Behavior**: Adapta-se a diferentes tamanhos de tela

##### Funcionalidades Avançadas:
- **Auto-collapse**: Fecha automaticamente após navegação
- **Dropdown Exclusivo**: Apenas um submenu aberto por vez
- **Highlight Inteligente**: Destaca rota ativa e expande submenu pai
- **Prevenção de Conflitos**: Evita fechamento acidental durante interação

#### 📱 Responsividade

- **Desktop (>768px)**: Hover para expandir, colapso automático
- **Tablet/Mobile (≤768px)**: Toggle manual, overlay modal
- **Touch Friendly**: Áreas de toque otimizadas para dispositivos móveis

## 🏗️ Funcionalidades do Sistema (Django)

### 👤 Gestão de Usuários

#### Tipos de Usuário
- **Master**: Acesso completo ao sistema
- **Restrito**: Permissões personalizáveis

#### Permissões Granulares
- Cadastrar clientes
- Cadastrar funcionários  
- Cadastrar cargos
- Agendar serviços
- Visualizar agendamentos
- Acessar relatórios

#### Funcionalidades
- ✅ Cadastro com validação completa
- ✅ Sistema de autenticação seguro
- ✅ Edição de perfis
- ✅ Controle de permissões
- ✅ Auditoria de ações

### 👥 Gestão de Funcionários

- **Cadastro Completo**: Nome, cargo, contato, informações pessoais
- **Vinculação com Usuários**: Funcionários podem ter acesso ao sistema
- **Controle de Cargos**: Hierarquia organizacional
- **Status de Atividade**: Ativar/desativar funcionários

### 👨‍💼 Gestão de Clientes

- **Cadastro Simplificado**: Dados essenciais para atendimento
- **Histórico de Agendamentos**: Visualização completa do relacionamento
- **Informações de Contato**: Telefone, email, endereço
- **Status de Cliente**: Controle de clientes ativos

### 📅 Sistema de Agendamentos

#### Funcionalidades Principais
- **Agendamento Completo**: Data, hora, cliente, funcionário, serviço
- **Controle de Status**: Agendado, em andamento, concluído, cancelado
- **Visualização Calendário**: Interface intuitiva para gestão
- **Histórico Completo**: Rastreamento de todos os agendamentos

#### Status de Agendamento
1. **Agendado** - Novo agendamento criado
2. **Em Andamento** - Serviço sendo executado
3. **Concluído** - Serviço finalizado
4. **Cancelado** - Agendamento cancelado

### 📊 Dashboard e Relatórios

#### Métricas Principais
- Total de usuários no sistema
- Quantidade de funcionários ativos
- Total de agendamentos
- Agendamentos do dia
- Receita mensal (se aplicável)

#### Relatórios Disponíveis
- **Agendamentos por Período**: Filtros customizáveis
- **Performance de Funcionários**: Produtividade individual
- **Análise de Clientes**: Frequência e relacionamento
- **Relatórios Financeiros**: Controle de receitas

### 🤖 Bot WhatsApp (Integração Meta)

#### Configurações da API
- **Token de Acesso**: Configuração da API do WhatsApp Business
- **Phone ID**: Identificação do número comercial
- **Webhook Token**: Verificação de segurança

#### Funcionalidades do Bot
- **Atendimento Automatizado**: Respostas programadas
- **Agendamento via WhatsApp**: Cliente pode agendar pelo chat
- **Confirmações Automáticas**: Notificações de agendamento
- **Fluxo Personalizable**: Configuração do comportamento do bot

### ⚙️ Configurações Empresariais

- **Dados da Empresa**: Nome, logo, informações de contato
- **Upload de Logo**: Sistema de upload com validação
- **Configurações Gerais**: Personalização do sistema
- **Backup de Configurações**: Exportação/importação de settings

## 🛠️ Implementação Django

### Estrutura Recomendada

```
jt_sistemas/
├── jt_sistemas/
│   ├── settings/
│   │   ├── __init__.py
│   │   ├── base.py
│   │   ├── development.py
│   │   └── production.py
│   ├── urls.py
│   └── wsgi.py
├── apps/
│   ├── usuarios/
│   │   ├── models.py
│   │   ├── views.py
│   │   ├── urls.py
│   │   ├── forms.py
│   │   └── admin.py
│   ├── funcionarios/
│   ├── clientes/
│   ├── agendamentos/
│   ├── relatorios/
│   └── configuracoes/
├── templates/
│   ├── base.html
│   ├── sidebar.html
│   └── dashboard.html
├── static/
│   ├── css/
│   ├── js/
│   └── images/
├── media/
├── requirements.txt
└── manage.py
```

### Models Django Principais

```python
# apps/usuarios/models.py
from django.contrib.auth.models import AbstractUser
from django.db import models

class Usuario(AbstractUser):
    TIPO_CHOICES = [
        ('master', 'Master'),
        ('restrito', 'Restrito'),
    ]
    
    tipo_usuario = models.CharField(max_length=20, choices=TIPO_CHOICES, default='restrito')
    nome = models.CharField(max_length=100)
    telefone = models.CharField(max_length=20, blank=True)
    
    # Permissões específicas
    pode_cadastrar_cliente = models.BooleanField(default=False)
    pode_cadastrar_funcionario = models.BooleanField(default=False)
    pode_cadastrar_cargo = models.BooleanField(default=False)
    pode_agendar = models.BooleanField(default=True)
    pode_ver_agendamentos = models.BooleanField(default=True)
    pode_ver_relatorios = models.BooleanField(default=False)

# apps/agendamentos/models.py
class Agendamento(models.Model):
    STATUS_CHOICES = [
        ('agendado', 'Agendado'),
        ('em_andamento', 'Em Andamento'),
        ('concluido', 'Concluído'),
        ('cancelado', 'Cancelado'),
    ]
    
    cliente = models.ForeignKey('usuarios.Usuario', on_delete=models.CASCADE)
    funcionario = models.ForeignKey('funcionarios.Funcionario', on_delete=models.CASCADE)
    servico = models.ForeignKey('servicos.Servico', on_delete=models.CASCADE)
    data_hora = models.DateTimeField()
    status = models.CharField(max_length=20, choices=STATUS_CHOICES, default='agendado')
    observacoes = models.TextField(blank=True)
    criado_em = models.DateTimeField(auto_now_add=True)
```

### Views Django com CBVs

```python
# apps/dashboard/views.py
from django.contrib.auth.mixins import LoginRequiredMixin
from django.views.generic import TemplateView

class DashboardView(LoginRequiredMixin, TemplateView):
    template_name = 'dashboard.html'
    
    def get_context_data(self, **kwargs):
        context = super().get_context_data(**kwargs)
        context['stats'] = {
            'total_usuarios': Usuario.objects.count(),
            'total_funcionarios': Funcionario.objects.count(),
            'total_agendamentos': Agendamento.objects.count(),
            'agendamentos_hoje': Agendamento.objects.filter(
                data_hora__date=timezone.now().date()
            ).count(),
        }
        return context
```

### Formulários Django

```python
# apps/usuarios/forms.py
from django import forms
from django.contrib.auth.forms import UserCreationForm
from .models import Usuario

class CadastroUsuarioForm(UserCreationForm):
    nome = forms.CharField(max_length=100, widget=forms.TextInput(attrs={
        'class': 'form-control',
        'placeholder': 'Nome completo'
    }))
    
    email = forms.EmailField(widget=forms.EmailInput(attrs={
        'class': 'form-control',
        'placeholder': 'email@exemplo.com'
    }))
    
    class Meta:
        model = Usuario
        fields = ('username', 'email', 'nome', 'password1', 'password2')
```

## 📦 Dependências Django

```python
# requirements.txt
Django>=4.2.0
django-crispy-forms>=1.14.0
crispy-bootstrap5>=0.7
Pillow>=9.0.0
django-extensions>=3.2.0
python-decouple>=3.6
whitenoise>=6.2.0
gunicorn>=20.1.0
psycopg2-binary>=2.9.0
celery>=5.2.0
redis>=4.3.0
django-cors-headers>=3.13.0
djangorestframework>=3.14.0
```

## 🚀 Configuração e Deploy

### Configurações de Desenvolvimento

```python
# settings/development.py
from .base import *

DEBUG = True
ALLOWED_HOSTS = ['localhost', '127.0.0.1']

DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.sqlite3',
        'NAME': BASE_DIR / 'db.sqlite3',
    }
}
```

### Configurações de Produção

```python
# settings/production.py
from .base import *
from decouple import config

DEBUG = False
ALLOWED_HOSTS = config('ALLOWED_HOSTS', cast=lambda v: [s.strip() for s in v.split(',')])

DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': config('DB_NAME'),
        'USER': config('DB_USER'),
        'PASSWORD': config('DB_PASSWORD'),
        'HOST': config('DB_HOST', default='localhost'),
        'PORT': config('DB_PORT', default='5432'),
    }
}
```

## 🎨 Frontend Moderno

### Bootstrap 5.3 + Custom CSS
- **Framework**: Bootstrap 5.3 para responsividade
- **Ícones**: Font Awesome 6.4.0
- **Fontes**: Inter (sistema) + JetBrains Mono (código)
- **Animações**: CSS Transitions + JavaScript
- **Componentes**: Cards, Modals, Dropdowns customizados

### JavaScript Modular
- **ES6+**: Classes e módulos modernos
- **Vanilla JS**: Sem dependências externas pesadas
- **Performance**: Lazy loading e otimizações
- **Acessibilidade**: ARIA labels e navegação por teclado

## 📱 Responsividade Completa

### Breakpoints
- **Mobile**: < 768px (Sidebar overlay)
- **Tablet**: 768px - 1024px (Sidebar adaptável)
- **Desktop**: > 1024px (Sidebar fixa com hover)

### Otimizações Mobile
- **Touch Targets**: Áreas de toque mínimas de 44px
- **Swipe Gestures**: Navegação por gestos
- **Performance**: Carregamento otimizado
- **Offline**: Service Worker para funcionalidades básicas

## 🔒 Segurança

### Autenticação e Autorização
- **Django Auth**: Sistema nativo do Django
- **Permissions**: Decorators e mixins customizados
- **Session Security**: Configurações seguras de sessão
- **CSRF Protection**: Proteção contra ataques CSRF

### Validações
- **Server-side**: Validação completa no backend
- **Client-side**: Validação instantânea no frontend
- **Sanitização**: Limpeza de dados de entrada
- **SQL Injection**: Proteção via ORM Django

## 📈 Performance

### Otimizações Backend
- **Database**: Índices otimizados e queries eficientes
- **Caching**: Redis para cache de sessões e dados
- **Static Files**: WhiteNoise para servir arquivos estáticos
- **Compression**: Compressão GZIP ativada

### Otimizações Frontend
- **Minificação**: CSS e JS minificados
- **Lazy Loading**: Carregamento sob demanda
- **Image Optimization**: Compressão automática de imagens
- **CDN Ready**: Preparado para CDN

## 🧪 Testes

### Estrutura de Testes
```python
# tests/test_usuarios.py
from django.test import TestCase
from django.contrib.auth import get_user_model

User = get_user_model()

class UsuarioTestCase(TestCase):
    def setUp(self):
        self.user = User.objects.create_user(
            username='testuser',
            email='test@example.com',
            nome='Usuário Teste'
        )
    
    def test_user_creation(self):
        self.assertEqual(self.user.username, 'testuser')
        self.assertTrue(self.user.is_active)
```

## 📚 Documentação da API

### Django REST Framework
```python
# apps/api/serializers.py
from rest_framework import serializers
from apps.agendamentos.models import Agendamento

class AgendamentoSerializer(serializers.ModelSerializer):
    class Meta:
        model = Agendamento
        fields = '__all__'
```

## 🤝 Contribuição

1. Fork o projeto
2. Crie uma branch para sua feature (`git checkout -b feature/nova-feature`)
3. Commit suas mudanças (`git commit -am 'Adiciona nova feature'`)
4. Push para a branch (`git push origin feature/nova-feature`)
5. Abra um Pull Request

## 📄 Licença

Este projeto está licenciado sob a Licença MIT - veja o arquivo [LICENSE](LICENSE) para detalhes.

## 🏆 Características Técnicas Destacadas

- ✅ **Arquitetura Moderna**: Django 4.2+ com boas práticas
- ✅ **UI/UX Premium**: Interface profissional e intuitiva
- ✅ **Responsividade Total**: Funciona em todos os dispositivos
- ✅ **Performance Otimizada**: Carregamento rápido e eficiente
- ✅ **Segurança Robusta**: Proteções contra vulnerabilidades comuns
- ✅ **Escalabilidade**: Preparado para crescimento
- ✅ **Manutenibilidade**: Código limpo e bem documentado
- ✅ **Testabilidade**: Estrutura preparada para testes
- ✅ **Deploy Ready**: Configurações para produção
- ✅ **API First**: Preparado para integrações futuras

---

**JT Sistemas** - Transformando a gestão empresarial com tecnologia moderna e design excepcional. 🚀