# Sintomas-do-C-ncer-cancer-symptoms-
Sintomas do Câncer(Câncer symptoms)
import { useState } from "react";

const CancerSymptomsWebsite = () => {
  const [activeTab, setActiveTab] = useState("geral");

  const symptomCategories = [
    {
      id: "geral",
      title: "Sintomas Gerais",
      symptoms: [
        {
          title: "Fadiga Persistente",
          description: "CansaÃ§o extremo que nÃ£o melhora com o descanso",
          image: "https://storage.googleapis.com/workspace-0f70711f-8b4e-4d94-86f1-2a93ccde5887/image/c0cc8aa1-fe70-48a0-a0fa-3839b1263674.png",
        },
        {
          title: "Perda de Peso Inexplicada",
          description: "Perder peso sem fazer dieta ou exercÃ­cios",
          image: "https://storage.googleapis.com/workspace-0f70711f-8b4e-4d94-86f1-2a93ccde5887/image/966842aa-755c-45fc-949c-f2850f9d8310.png",
        },
      ],
    },
    {
      id: "pele",
      title: "Sinais na Pele",
      symptoms: [
        {
          title: "MudanÃ§as em Pintas",
          description: "Pintas que mudam de cor, tamanho ou forma",
          image: "https://storage.googleapis.com/workspace-0f70711f-8b4e-4d94-86f1-2a93ccde5887/image/2257389a-747a-487b-981a-904fb468faa8.png",
        },
        {
          title: "Feridas que nÃ£o Cicatrizam",
          description: "Feridas que demoram mais de 4 semanas para sarar",
          image: "https://storage.googleapis.com/workspace-0f70711f-8b4e-4d94-86f1-2a93ccde5887/image/07cc793b-9292-4b29-bd30-e6bef3a14235.png",
        },
      ],
    },
    {
      id: "digestivo",
      title: "Sistema Digestivo",
      symptoms: [
        {
          title: "Dificuldade para Engolir",
          description: "SensaÃ§Ã£o de comida presa na garganta",
          image: "https://storage.googleapis.com/workspace-0f70711f-8b4e-4d94-86f1-2a93ccde5887/image/dd4eb374-e914-4821-bb1d-e5f2d76ed36b.png",
        },
        {
          title: "MudanÃ§as nos HÃ¡bitos Intestinais",
          description: "Diarreia ou constipaÃ§Ã£o persistentes",
          image: "https://storage.googleapis.com/workspace-0f70711f-8b4e-4d94-86f1-2a93ccde5887/image/e0f3a7e8-ee1a-41d2-8608-36cddd967a79.png",
        },
      ],
    },
  ];

  return (
    <div className="min-h-screen bg-white">
      {/* Header */}
      <header className="bg-blue-600 text-white py-6">
        <div className="container mx-auto px-4">
          <h1 className="text-3xl font-bold text-center">Sintomas do CÃ¢ncer</h1>
          <p className="text-center mt-2">Reconhecer os sinais precocemente pode salvar vidas</p>
        </div>
      </header>

      {/* Navigation Tabs */}
      <nav className="bg-gray-100 border-b">
        <div className="container mx-auto px-4">
          <div className="flex flex-wrap gap-2 py-4">
            {symptomCategories.map((category) => (
              <button
                key={category.id}
                onClick={() => setActiveTab(category.id)}
                className={`px-4 py-2 rounded-lg font-medium transition-colors ${
                  activeTab === category.id
                    ? "bg-blue-600 text-white"
                    : "bg-white text-gray-700 hover:bg-gray-200"
                }`}
              >
                {category.title}
              </button>
            ))}
          </div>
        </div>
      </nav>

      {/* Main Content */}
      <main className="container mx-auto px-4 py-8">
        <div className="max-w-4xl mx-auto">
          <h2 className="text-2xl font-bold text-gray-800 mb-6">
            {symptomCategories.find((cat) => cat.id === activeTab)?.title}
          </h2>

          <div className="space-y-8">
            {symptomCategories
              .find((cat) => cat.id === activeTab)
              ?.symptoms.map((symptom, index) => (
                <div
                  key={index}
                  className="bg-white rounded-lg shadow-md overflow-hidden hover:shadow-lg transition-shadow"
                >
                  <div className="md:flex">
                    <div className="md:flex-shrink-0 md:w-64">
                      <img
                        src={symptom.image}
                        alt={`Imagem ilustrativa de ${symptom.title} mostrando os sinais visÃ­veis dessa condiÃ§Ã£o mÃ©dica`}
                        className="w-full h-48 object-cover"
                      />
                    </div>
                    <div className="p-6">
                      <h3 className="text-xl font-semibold text-gray-800 mb-2">
                        {symptom.title}
                      </h3>
                      <p className="text-gray-600 mb-4">{symptom.description}</p>
                      <div className="bg-yellow-50 border-l-4 border-yellow-400 p-4">
                        <p className="text-yellow-700 text-sm">
                          Procure um mÃ©dico se este sintoma persistir por mais de 2 semanas
                        </p>
                      </div>
                    </div>
                  </div>
                </div>
              ))}
          </div>
        </div>
      </main>

      {/* Important Notice */}
      <section className="bg-red-50 border-t border-b border-red-200 py-8">
        <div className="container mx-auto px-4">
          <div className="max-w-4xl mx-auto text-center">
            <h2 className="text-2xl font-bold text-red-800 mb-4">âš ï¸ Aviso Importante</h2>
            <p className="text-red-700">
              Este site Ã© apenas para fins informativos. Muitos desses sintomas podem ser causados
              por condiÃ§Ãµes menos graves. Sempre consulte um mÃ©dico para um diagnÃ³stico adequado.
              O diagnÃ³stico precoce Ã© fundamental para o sucesso do tratamento do cÃ¢ncer.
            </p>
          </div>
        </div>
      </section>

      {/* Footer */}
      <footer className="bg-gray-800 text-white py-8">
        <div className="container mx-auto px-4 text-center">
          <p>Â© 2024 InformaÃ§Ãµes sobre SaÃºde. Todos os direitos reservados.</p>
          <p className="mt-2 text-gray-400 text-sm">
            Consulte sempre profissionais de saÃºde para orientaÃ§Ãµes mÃ©dicas
          </p>
        </div>
      </footer>
    </div>
  );
};

export default CancerSymptomsWebsite;
