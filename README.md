import React, { useState } from 'react';
import { Instagram, Calendar, MapPin, Users, Award, ChevronRight } from 'lucide-react';

export default function EventoSaudeUnica() {
  const [activeSection, setActiveSection] = useState('inicio');

  const fotosAntes = [
    { id: 2, descricao: "Situação antes da intervenção - Acúmulo de materiais" },
    { id: 5, descricao: "Área com condições precárias" }
  ];

  const fotosDepois = [
    { id: 3, descricao: "Equipe mobilizada para ação" },
    { id: 4, descricao: "Trabalho de campo - Identificação de focos" }
  ];

  return (
    <div className="min-h-screen bg-gray-50">
      {/* Header - Estilo Prefeitura */}
      <header className="bg-blue-900 text-white shadow-lg">
        <div className="container mx-auto px-4 py-4">
          <div className="flex items-center justify-between">
            <div className="flex items-center space-x-4">
              <div className="w-16 h-16 bg-white rounded-full flex items-center justify-center">
                <span className="text-blue-900 font-bold text-xs text-center">MATINHOS<br/>PR</span>
              </div>
              <div>
                <h1 className="text-2xl font-bold">Prefeitura Municipal de Matinhos</h1>
                <p className="text-sm text-blue-200">Integração Saúde/Ambiente</p>
              </div>
            </div>
            <a 
              href="https://www.instagram.com/integracaosaudee?igsh=ZjY2OGJ0cHJteGo5&utm_source=qr"
              target="_blank"
              rel="noopener noreferrer"
              className="flex items-center gap-2 bg-gradient-to-r from-purple-600 to-pink-600 px-6 py-3 rounded-full hover:from-purple-700 hover:to-pink-700 transition-all transform hover:scale-105"
            >
              <Instagram className="w-5 h-5" />
              <span className="font-semibold">Siga-nos</span>
            </a>
          </div>
        </div>
      </header>

      {/* Navigation */}
      <nav className="bg-blue-800 text-white shadow">
        <div className="container mx-auto px-4">
          <div className="flex space-x-1">
            {['inicio', 'projeto', 'galeria', 'video'].map((section) => (
              <button
                key={section}
                onClick={() => setActiveSection(section)}
                className={`px-6 py-3 font-semibold transition-colors ${
                  activeSection === section 
                    ? 'bg-blue-900 border-b-4 border-yellow-400' 
                    : 'hover:bg-blue-700'
                }`}
              >
                {section === 'inicio' && 'Início'}
                {section === 'projeto' && 'O Projeto'}
                {section === 'galeria' && 'Galeria'}
                {section === 'video' && 'Apresentação'}
              </button>
            ))}
          </div>
        </div>
      </nav>

      {/* Banner Principal */}
      <div className="bg-gradient-to-r from-green-600 to-blue-600 text-white py-16">
        <div className="container mx-auto px-4 text-center">
          <div className="inline-block bg-white text-green-700 px-4 py-2 rounded-full mb-4 font-semibold">
            I Simpósio Internacional One Health UFPR 2025
          </div>
          <h2 className="text-5xl font-bold mb-4">Integração Saúde/Ambiente</h2>
          <p className="text-2xl mb-6">Experiência Exitosa de Combate à Dengue em Pontos Estratégicos</p>
          <div className="flex justify-center gap-8 text-lg">
            <div className="flex items-center gap-2">
              <Calendar className="w-6 h-6" />
              <span>13 e 14 de Novembro de 2025</span>
            </div>
            <div className="flex items-center gap-2">
              <MapPin className="w-6 h-6" />
              <span>Matinhos, Paraná</span>
            </div>
          </div>
        </div>
      </div>

      {/* Conteúdo Principal */}
      <main className="container mx-auto px-4 py-12">
        
        {/* Seção Início */}
        {activeSection === 'inicio' && (
          <div className="space-y-8">
            <div className="bg-white rounded-lg shadow-lg p-8">
              <div className="flex items-center gap-3 mb-6">
                <Award className="w-8 h-8 text-green-600" />
                <h3 className="text-3xl font-bold text-gray-800">Sobre o Evento</h3>
              </div>
              <p className="text-lg text-gray-700 mb-4 leading-relaxed">
                O projeto "Integração Saúde-Ambiente-Trabalho" foi apresentado no I Simpósio Internacional 
                One Health UFPR 2025, realizado nos dias 13 e 14 de novembro de 2025, demonstrando uma 
                abordagem integrada e participativa no combate à dengue em Matinhos/PR.
              </p>
              <p className="text-lg text-gray-700 leading-relaxed">
                Esta iniciativa representa um marco na saúde pública municipal, unindo esforços dos setores 
                de saúde, meio ambiente e trabalho para fortalecer ações educativas e preventivas voltadas 
                à eliminação de criadouros e à proteção de ambientes laborais saudáveis.
              </p>
            </div>

            {/* Cards de Destaque */}
            <div className="grid md:grid-cols-3 gap-6">
              <div className="bg-green-50 border-l-4 border-green-600 p-6 rounded-lg">
                <Users className="w-10 h-10 text-green-600 mb-3" />
                <h4 className="font-bold text-xl mb-2 text-gray-800">Participativo</h4>
                <p className="text-gray-700">Estratégia intersetorial envolvendo profissionais e comunidade</p>
              </div>
              <div className="bg-blue-50 border-l-4 border-blue-600 p-6 rounded-lg">
                <MapPin className="w-10 h-10 text-blue-600 mb-3" />
                <h4 className="font-bold text-xl mb-2 text-gray-800">Pontos Estratégicos</h4>
                <p className="text-gray-700">Ações focadas em locais de alto risco identificados tecnicamente</p>
              </div>
              <div className="bg-yellow-50 border-l-4 border-yellow-600 p-6 rounded-lg">
                <Award className="w-10 h-10 text-yellow-600 mb-3" />
                <h4 className="font-bold text-xl mb-2 text-gray-800">Resultados</h4>
                <p className="text-gray-700">Melhorias significativas nas condições ambientais e de saúde</p>
              </div>
            </div>
          </div>
        )}

        {/* Seção Projeto */}
        {activeSection === 'projeto' && (
          <div className="space-y-8">
            <div className="bg-white rounded-lg shadow-lg p-8">
              <h3 className="text-3xl font-bold text-gray-800 mb-6">O Projeto</h3>
              
              <div className="space-y-6">
                <div>
                  <h4 className="text-2xl font-semibold text-green-700 mb-3">Introdução</h4>
                  <p className="text-gray-700 leading-relaxed">
                    A dengue é uma das principais preocupações de saúde pública no Brasil, especialmente 
                    em municípios litorâneos com alta densidade populacional e clima favorável à proliferação 
                    do vetor <em>Aedes aegypti</em>. Em Matinhos/PR, a integração entre os setores de saúde, 
                    meio ambiente e trabalho foi essencial para fortalecer ações educativas e preventivas 
                    voltadas à eliminação de criadouros e à proteção de ambientes laborais saudáveis.
                  </p>
                </div>

                <div className="bg-blue-50 p-6 rounded-lg">
                  <h4 className="text-2xl font-semibold text-blue-700 mb-3">Metodologia</h4>
                  <p className="text-gray-700 mb-4 leading-relaxed">
                    O projeto foi desenvolvido por meio de visitas técnicas dos Agentes de Combate às 
                    Endemias (ACEs) a pontos estratégicos, com mapeamento e classificação de locais por 
                    risco. Foram observadas vivências do ambiente, vulnerabilidades relacionadas ao acúmulo 
                    de materiais e exposição a riscos ocupacionais.
                  </p>
                  <p className="text-gray-700 leading-relaxed">
                    Foram propostas melhorias no armazenamento de materiais, uso de equipamentos de proteção 
                    individual (EPIs) e aplicação do Plano Nacional de Controle da Dengue (PNCD). 
                    Posteriormente, realizou-se ação educativa integrada, em evento comemorativo ao Dia 
                    Mundial da Saúde e ao Mês de Prevenção aos Acidentes de Trabalho.
                  </p>
                </div>

                <div>
                  <h4 className="text-2xl font-semibold text-green-700 mb-3">Objetivos</h4>
                  <p className="text-gray-700 leading-relaxed">
                    Promover a saúde ambiental e a saúde do trabalhador por meio da mobilização de 
                    profissionais e gestores de pontos estratégicos de Matinhos/PR, com foco em ações 
                    educativas de controle de agravos, prevenção de agravos e melhoria das condições de 
                    trabalho e qualidade de vida.
                  </p>
                </div>

                <div className="bg-green-50 p-6 rounded-lg">
                  <h4 className="text-2xl font-semibold text-green-700 mb-4">Resultados</h4>
                  
                  <div className="mb-6">
                    <h5 className="font-bold text-lg mb-3 text-gray-800">Atividades Realizadas</h5>
                    <div className="overflow-x-auto">
                      <table className="w-full border-collapse">
                        <thead>
                          <tr className="bg-green-600 text-white">
                            <th className="border border-green-700 px-4 py-2 text-left">Atividade/Serviço</th>
                            <th className="border border-green-700 px-4 py-2">Quantidade</th>
                            <th className="border border-green-700 px-4 py-2 text-left">Público Atingido</th>
                          </tr>
                        </thead>
                        <tbody className="text-gray-700">
                          <tr className="bg-white">
                            <td className="border border-gray-300 px-4 py-2">Testes rápidos (HIV, sífilis, Hep. B e C)</td>
                            <td className="border border-gray-300 px-4 py-2 text-center">32</td>
                            <td className="border border-gray-300 px-4 py-2">Trabalhadores e comunidade</td>
                          </tr>
                          <tr className="bg-gray-50">
                            <td className="border border-gray-300 px-4 py-2">Vacinas (DT, dT, B)</td>
                            <td className="border border-gray-300 px-4 py-2 text-center">8</td>
                            <td className="border border-gray-300 px-4 py-2">Trabalhadores e comunidade</td>
                          </tr>
                          <tr className="bg-white">
                            <td className="border border-gray-300 px-4 py-2">Palestras educativas</td>
                            <td className="border border-gray-300 px-4 py-2 text-center">2</td>
                            <td className="border border-gray-300 px-4 py-2">Catadores e comunidade local</td>
                          </tr>
                          <tr className="bg-gray-50">
                            <td className="border border-gray-300 px-4 py-2">Espaço educativo infantil</td>
                            <td className="border border-gray-300 px-4 py-2 text-center">1</td>
                            <td className="border border-gray-300 px-4 py-2">Crianças acompanhando os trabalhadores</td>
                          </tr>
                          <tr className="bg-white">
                            <td className="border border-gray-300 px-4 py-2">Materiais informativos distribuídos</td>
                            <td className="border border-gray-300 px-4 py-2 text-center">-</td>
                            <td className="border border-gray-300 px-4 py-2">População geral</td>
                          </tr>
                        </tbody>
                      </table>
                    </div>
                  </div>

                  <div>
                    <h5 className="font-bold text-lg mb-3 text-gray-800">Melhorias Observadas</h5>
                    <div className="overflow-x-auto">
                      <table className="w-full border-collapse">
                        <thead>
                          <tr className="bg-green-600 text-white">
                            <th className="border border-green-700 px-4 py-2 text-left">Aspecto Avaliado</th>
                            <th className="border border-green-700 px-4 py-2">Situação Antes</th>
                            <th className="border border-green-700 px-4 py-2">Situação Após</th>
                          </tr>
                        </thead>
                        <tbody className="text-gray-700">
                          <tr className="bg-white">
                            <td className="border border-gray-300 px-4 py-2">Organização dos depósitos</td>
                            <td className="border border-gray-300 px-4 py-2 text-center">Precária</td>
                            <td className="border border-gray-300 px-4 py-2 text-center">Mais estruturada</td>
                          </tr>
                          <tr className="bg-gray-50">
                            <td className="border border-gray-300 px-4 py-2">Uso de EPIs</td>
                            <td className="border border-gray-300 px-4 py-2 text-center">Raro</td>
                            <td className="border border-gray-300 px-4 py-2 text-center">Ampliado</td>
                          </tr>
                          <tr className="bg-white">
                            <td className="border border-gray-300 px-4 py-2">Armazenamento de materiais recicláveis</td>
                            <td className="border border-gray-300 px-4 py-2 text-center">Descoberto</td>
                            <td className="border border-gray-300 px-4 py-2 text-center">Cobertura construída</td>
                          </tr>
                          <tr className="bg-gray-50">
                            <td className="border border-gray-300 px-4 py-2">Valorização do trabalho</td>
                            <td className="border border-gray-300 px-4 py-2 text-center">Baixa</td>
                            <td className="border border-gray-300 px-4 py-2 text-center">Reconhecimento social</td>
                          </tr>
                          <tr className="bg-white">
                            <td className="border border-gray-300 px-4 py-2">Conhecimento sobre prevenção da dengue</td>
                            <td className="border border-gray-300 px-4 py-2 text-center">Limitado</td>
                            <td className="border border-gray-300 px-4 py-2 text-center">Ampliado</td>
                          </tr>
                        </tbody>
                      </table>
                    </div>
                  </div>
                </div>

                <div className="bg-gray-50 p-6 rounded-lg">
                  <h4 className="text-2xl font-semibold text-gray-800 mb-3">Agradecimentos</h4>
                  <ul className="space-y-2 text-gray-700">
                    <li className="flex items-start gap-2">
                      <ChevronRight className="w-5 h-5 text-green-600 mt-1 flex-shrink-0" />
                      <span>Prefeitura Municipal de Matinhos</span>
                    </li>
                    <li className="flex items-start gap-2">
                      <ChevronRight className="w-5 h-5 text-green-600 mt-1 flex-shrink-0" />
                      <span>Secretaria Municipal de Saúde</span>
                    </li>
                    <li className="flex items-start gap-2">
                      <ChevronRight className="w-5 h-5 text-green-600 mt-1 flex-shrink-0" />
                      <span>Vigilância em Saúde e Ambiente</span>
                    </li>
                  </ul>
                </div>
              </div>
            </div>
          </div>
        )}

        {/* Seção Galeria */}
        {activeSection === 'galeria' && (
          <div className="space-y-8">
            <div className="bg-white rounded-lg shadow-lg p-8">
              <h3 className="text-3xl font-bold text-gray-800 mb-6">Galeria: Antes e Depois</h3>
              
              <div className="mb-12">
                <h4 className="text-2xl font-semibold text-red-700 mb-4">Situação Antes da Intervenção</h4>
                <div className="grid md:grid-cols-2 gap-6">
                  {fotosAntes.map((foto) => (
                    <div key={foto.id} className="border-4 border-red-200 rounded-lg overflow-hidden">
                      <div className="bg-red-50 p-4 text-center">
                        <p className="font-semibold text-gray-800">{foto.descricao}</p>
                        <p className="text-sm text-gray-600 mt-1">Imagem {foto.id}</p>
                      </div>
                    </div>
                  ))}
                </div>
              </div>

              <div>
                <h4 className="text-2xl font-semibold text-green-700 mb-4">Ação e Resultados</h4>
                <div className="grid md:grid-cols-2 gap-6">
                  {fotosDepois.map((foto) => (
                    <div key={foto.id} className="border-4 border-green-200 rounded-lg overflow-hidden">
                      <div className="bg-green-50 p-4 text-center">
                        <p className="font-semibold text-gray-800">{foto.descricao}</p>
                        <p className="text-sm text-gray-600 mt-1">Imagem {foto.id}</p>
                      </div>
                    </div>
                  ))}
                </div>
              </div>
            </div>
          </div>
        )}

        {/* Seção Vídeo */}
        {activeSection === 'video' && (
          <div className="space-y-8">
            <div className="bg-gradient-to-br from-purple-100 to-pink-100 rounded-lg shadow-xl p-8 border-4 border-purple-300">
              <div className="text-center mb-8">
                <h3 className="text-4xl font-bold text-gray-800 mb-3">🎥 Apresentação do Trabalho</h3>
                <p className="text-xl text-gray-700">Assista à apresentação completa do projeto no Instagram</p>
              </div>
              
              <div className="max-w-3xl mx-auto">
                <div className="bg-white rounded-2xl shadow-2xl p-8 text-center">
                  <div className="mb-6">
                    <div className="w-32 h-32 mx-auto bg-gradient-to-br from-purple-600 to-pink-600 rounded-full flex items-center justify-center mb-4 shadow-lg">
                      <Instagram className="w-16 h-16 text-white" />
                    </div>
                    <h4 className="text-2xl font-bold text-gray-800 mb-2">Vídeo de Apresentação</h4>
                    <p className="text-gray-600">Confira todos os detalhes do projeto apresentado no simpósio</p>
                  </div>
                  
                  <a 
                    href="https://www.instagram.com/reel/DRcp4WiDi0H/?igsh=ZzkxbDQxajQ0MGIw"
                    target="_blank"
                    rel="noopener noreferrer"
                    className="inline-flex items-center gap-3 bg-gradient-to-r from-purple-600 to-pink-600 text-white px-10 py-5 rounded-full text-xl font-bold hover:from-purple-700 hover:to-pink-700 transition-all transform hover:scale-105 shadow-lg"
                  >
                    <Instagram className="w-8 h-8" />
                    <span>Assistir no Instagram</span>
                  </a>
                  
                  <div className="mt-8 pt-6 border-t border-gray-200">
                    <p className="text-gray-600 mb-4">Siga nosso perfil para mais atualizações:</p>
                    <a 
                      href="https://www.instagram.com/integracaosaudee?igsh=ZjY2OGJ0cHJteGo5&utm_source=qr"
                      target="_blank"
                      rel="noopener noreferrer"
                      className="inline-flex items-center gap-2 text-purple-700 hover:text-purple-900 font-semibold text-lg"
                    >
                      <Instagram className="w-6 h-6" />
                      @integracaosaudee
                    </a>
                  </div>
                </div>
              </div>
            </div>
          </div>
        )}

      </main>

      {/* Footer */}
      <footer className="bg-blue-900 text-white py-8 mt-12">
        <div className="container mx-auto px-4">
          <div className="grid md:grid-cols-3 gap-8 mb-6">
            <div>
              <h4 className="font-bold text-lg mb-3">Contato</h4>
              <p className="text-blue-200">Prefeitura Municipal de Matinhos</p>
              <p className="text-blue-200">Matinhos - Paraná</p>
            </div>
            <div>
              <h4 className="font-bold text-lg mb-3">Redes Sociais</h4>
              <a 
                href="https://www.instagram.com/integracaosaudee?igsh=ZjY2OGJ0cHJteGo5&utm_source=qr"
                target="_blank"
                rel="noopener noreferrer"
                className="flex items-center gap-2 text-blue-200 hover:text-white transition-colors"
              >
                <Instagram className="w-5 h-5" />
                @integracaosaudee
              </a>
            </div>
            <div>
              <h4 className="font-bold text-lg mb-3">Evento</h4>
              <p className="text-blue-200">I Simpósio Internacional One Health</p>
              <p className="text-blue-200">UFPR 2025</p>
            </div>
          </div>
          <div className="border-t border-blue-800 pt-6 text-center">
            <p className="text-blue-200">© 2025 Prefeitura Municipal de Matinhos - Todos os direitos reservados</p>
            <p className="text-blue-300 mt-2 text-sm">Integração Saúde/Ambiente - Diálogos em Saúde Única</p>
          </div>
        </div>
      </footer>
    </div>
  );
}
