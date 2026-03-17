/**
 * @file manual_interactivo.jsx
 * @description Plataforma de Gestión de Comercio Exterior y Aduanas
 * @company González Robles & Asociados
 * @version 6.5.0 (Actualización 2026)
 * * Este archivo contiene la aplicación completa en un solo componente funcional
 * diseñado para gestionar operaciones de despacho aduanero, consultoría técnica
 * y gestión de clientes de alta gama (Max Mara) y mercancía crítica (Buche de Pescado).
 */

import React, { useState, useMemo } from 'react';
import { 
  ChevronRight, 
  Package, 
  ShieldCheck, 
  Globe, 
  Truck, 
  FileText, 
  BarChart3, 
  Info,
  CheckCircle2,
  AlertCircle,
  Menu,
  Search,
  Gavel,
  PhoneCall,
  Lock,
  ArrowRightLeft,
  BookOpen,
  Tag,
  Scale,
  Users,
  Store,
  MapPin,
  ExternalLink,
  Loader2,
  Plus,
  X,
  Building2,
  Fish,
  Eye,
  History,
  ClipboardCheck,
  Settings,
  Download
} from 'lucide-react';

// --- CONFIGURACIÓN DE API ---
// La ejecución requiere una clave de API de Gemini configurada en el entorno
const apiKey = "";

const App = () => {
  // --- ESTADOS GLOBALES ---
  const [activeTab, setActiveTab] = useState('dashboard');
  const [sidebarOpen, setSidebarOpen] = useState(true);
  const [searchQuery, setSearchQuery] = useState('');
  const [searchResults, setSearchResults] = useState(null);
  const [isSearching, setIsSearching] = useState(false);
  const [selectedClient, setSelectedClient] = useState(null);

  // --- BASE DE DATOS LOCAL (SIMULADA) ---
  const [clients, setClients] = useState([
    { id: 'mm-01', name: "Max Mara", sector: "Textil / Lujo", status: "Activo", priority: "VIP Alta", icon: "MM", info: "Líder en retail de lujo italiano. Enfoque en abrigos y accesorios de alta gama." },
    { id: 'bp-04', name: "Buche de Pescado", sector: "Pesca / Exportación", status: "Activo", priority: "Crítica", icon: "BP", info: "Operación especializada en vejigas natatorias (Maw). Vigilancia CITES y PROFEPA." },
    { id: 'ga-02', name: "Giorgio Armani", sector: "Textil", status: "Activo", priority: "Media", icon: "GA", info: "Importación de sastrería y accesorios masculinos." },
    { id: 'vs-03', name: "Versace", sector: "Lujo / Accesorios", status: "En Proceso", priority: "Alta", icon: "VS", info: "Gestión de marroquinería y complementos de moda." },
  ]);

  const [isAddingClient, setIsAddingClient] = useState(false);

  // --- LÓGICA DE NEGOCIO ---

  const handleAddClient = (newClient) => {
    const clientWithId = {
      ...newClient,
      id: `custom-${Date.now()}`,
      icon: newClient.name.substring(0, 2).toUpperCase(),
    };
    setClients([...clients, clientWithId]);
    setIsAddingClient(false);
  };

  const handleSearch = async (e) => {
    e.preventDefault();
    if (!searchQuery) return;
    setIsSearching(true);
    setSearchResults(null);
    try {
      const response = await fetch(`https://generativelanguage.googleapis.com/v1beta/models/gemini-2.5-flash-preview-09-2025:generateContent?key=${apiKey}`, {
        method: 'POST',
        headers: { 'Content-Type': 'application/json' },
        body: JSON.stringify({
          contents: [{ parts: [{ text: `Actúa como un experto en comercio exterior mexicano. Busca información técnica aduanera para: ${searchQuery}. Detalla fracciones LIGIE 2026, NICOs y RRNAs (NOMs, permisos).` }] }],
          tools: [{ "google_search": {} }]
        })
      });
      const result = await response.json();
      const text = result.candidates?.[0]?.content?.parts?.[0]?.text || "No se pudo obtener información técnica en este momento.";
      const sources = result.candidates?.[0]?.groundingMetadata?.groundingAttributions?.map(a => ({ uri: a.web?.uri, title: a.web?.title })) || [];
      
      setSearchResults({ text, sources });
    } catch (error) { 
      console.error("Error en consulta técnica:", error);
    } finally { 
      setIsSearching(false); 
    }
  };

  const navigateToClientDetail = (client) => {
    setSelectedClient(null);
    if (client.id === 'mm-01') {
      setActiveTab('maxmara');
    } else if (client.id === 'bp-04') {
      setActiveTab('buche');
    } else {
      setSelectedClient(client);
      setActiveTab('client-detail');
    }
  };

  // --- COMPONENTES DE NAVEGACIÓN ---

  const sections = [
    { id: 'dashboard', label: 'Panel Global', icon: <Globe size={20} /> },
    { id: 'clients', label: 'Cartera de Clientes', icon: <Users size={20} /> },
    { id: 'maxmara', label: 'Max Mara (VIP)', icon: <Store size={20} /> },
    { id: 'buche', label: 'Buche de Pescado', icon: <Fish size={20} /> },
    { id: 'ligie', label: 'LIGIE 2026 & NICOs', icon: <BookOpen size={20} /> },
    { id: 'legal', label: 'Marco Jurídico', icon: <Scale size={20} /> },
    { id: 'emergency', label: 'Protocolos PAMA/SOS', icon: <AlertCircle size={20} /> },
  ];

  const renderContent = () => {
    switch (activeTab) {
      case 'dashboard': return <DashboardView setActiveTab={setActiveTab} clientsCount={clients.length} />;
      case 'clients': return (
        <ClientsGeneralView 
          clients={clients} 
          onSelect={navigateToClientDetail} 
          onAdd={() => setIsAddingClient(true)} 
        />
      );
      case 'client-detail': return <ClientDetailView client={selectedClient} onBack={() => setActiveTab('clients')} />;
      case 'maxmara': return <MaxMaraView onBack={() => setActiveTab('clients')} />;
      case 'buche': return <BuchePescadoView onBack={() => setActiveTab('clients')} />;
      case 'ligie': return <LigieView />;
      case 'legal': return <LegalFrameworkView />;
      case 'emergency': return <EmergencyView />;
      default: return <DashboardView setActiveTab={setActiveTab} clientsCount={clients.length} />;
    }
  };

  return (
    <div className="flex h-screen bg-[#F1F5F9] text-slate-900 font-sans overflow-hidden">
      {/* Sidebar Corporativo */}
      <div className={`${sidebarOpen ? 'w-72' : 'w-20'} bg-[#0F172A] text-white transition-all duration-300 flex flex-col z-20 shadow-2xl`}>
        <div className="p-6 flex items-center gap-3 border-b border-white/10 min-h-[80px]">
          <div className="bg-emerald-500 text-white p-2 rounded-lg shrink-0 shadow-lg shadow-emerald-500/20">
            <Building2 size={24} />
          </div>
          {sidebarOpen && (
            <div className="flex flex-col leading-tight animate-in fade-in slide-in-from-left-2">
              <span className="font-bold tracking-tight text-base uppercase">González Robles</span>
              <span className="text-[10px] font-medium text-slate-400">& Asociados</span>
            </div>
          )}
        </div>
        
        <nav className="flex-1 py-6 px-3 space-y-1 overflow-y-auto custom-scrollbar">
          {sections.map((section) => (
            <button key={section.id} 
              onClick={() => { setActiveTab(section.id); setSelectedClient(null); setSearchResults(null); }}
              className={`w-full flex items-center gap-3 px-3 py-3 rounded-xl transition-all duration-200 ${
                activeTab === section.id 
                ? 'bg-emerald-600 text-white shadow-lg shadow-emerald-600/20' 
                : 'text-slate-400 hover:text-white hover:bg-white/5'
              }`}>
              <span className="shrink-0">{section.icon}</span>
              {sidebarOpen && <span className="font-medium text-sm text-left truncate">{section.label}</span>}
            </button>
          ))}
        </nav>

        <div className="p-4 border-t border-white/5 text-[9px] text-slate-500 font-bold uppercase tracking-widest text-center">
          {sidebarOpen ? 'Consultoría Aduanera 2026' : 'GR&A'}
        </div>
      </div>

      {/* Main Container */}
      <div className="flex-1 flex flex-col overflow-hidden relative">
        <header className="h-20 bg-white border-b border-slate-200 flex items-center justify-between px-8 z-10 shadow-sm">
          <div className="flex items-center gap-4 flex-1">
            <button onClick={() => setSidebarOpen(!sidebarOpen)} className="p-2 hover:bg-slate-50 rounded-lg transition-colors text-slate-600">
              <Menu size={20} />
            </button>
            <form onSubmit={handleSearch} className="relative w-full max-w-md hidden md:block group">
              <input 
                type="text" 
                placeholder="Inteligencia Aduanera (Fracciones, NICOs, Leyes)..." 
                className="w-full pl-10 pr-4 py-2.5 bg-slate-50 border border-slate-200 rounded-full text-sm focus:ring-2 focus:ring-emerald-500 focus:bg-white focus:border-emerald-500 outline-none transition-all shadow-inner" 
                value={searchQuery} 
                onChange={(e) => setSearchQuery(e.target.value)} 
              />
              <div className="absolute left-3 top-3 text-slate-400 group-focus-within:text-emerald-500 transition-colors">
                <Search size={18} />
              </div>
            </form>
          </div>

          <div className="flex items-center gap-6">
            <div className="flex flex-col text-right hidden lg:block">
              <span className="text-[10px] font-black text-slate-400 uppercase tracking-widest">Portal Administrativo</span>
              <p className="text-sm font-bold text-slate-800 tracking-tight italic">Operativa Internacional</p>
            </div>
            <div className="w-10 h-10 bg-[#0F172A] border border-white/10 rounded-full flex items-center justify-center font-bold text-white shadow-xl">GR</div>
          </div>
        </header>

        <main className="flex-1 overflow-y-auto p-8 bg-[#F8FAFC]">
          <div className="max-w-6xl mx-auto space-y-8 pb-12">
            
            {/* Search Results / Intelligence Overlay */}
            {isSearching && <SearchLoader />}
            {searchResults && !isSearching && <SearchResults results={searchResults} onClose={() => setSearchResults(null)} />}
            
            {renderContent()}
          </div>
        </main>
      </div>

      {/* Alta de Cliente Modal */}
      {isAddingClient && <AddClientModal onAdd={handleAddClient} onClose={() => setIsAddingClient(false)} />}
    </div>
  );
};

// --- VISTAS PRINCIPALES ---

const DashboardView = ({ setActiveTab, clientsCount }) => (
  <div className="space-y-8 animate-in fade-in duration-500">
    <div className="flex flex-col md:flex-row justify-between items-start md:items-end gap-6 border-b border-slate-200 pb-8">
      <div>
        <h1 className="text-4xl font-light text-slate-900 mb-2 tracking-tight">González Robles <span className="font-bold text-emerald-600 italic text-5xl">& Asociados</span></h1>
        <p className="text-slate-500 text-lg">Plataforma Inteligente de Despacho Aduanero y Consultoría Técnica.</p>
      </div>
      <div className="flex gap-4">
        <KPIBoxSmall label="Clientes" value={clientsCount} color="blue" />
        <KPIBoxSmall label="Cumplimiento" value="100%" color="emerald" />
      </div>
    </div>

    <div className="grid grid-cols-1 md:grid-cols-4 gap-4">
      <Card title="Cartera General" desc="Administración de socios." icon={<Users size={22} className="text-blue-600" />} onClick={() => setActiveTab('clients')} status="Empresas" />
      <Card title="Portal Max Mara" desc="Protocolos de retail lujo." icon={<Store size={22} className="text-purple-600" />} onClick={() => setActiveTab('maxmara')} status="VIP" />
      <Card title="Buche Pescado" desc="CITES & Vida Silvestre." icon={<Fish size={22} className="text-emerald-600" />} onClick={() => setActiveTab('buche')} status="Crítico" />
      <Card title="Protocolos SOS" desc="PAMAs y contingencias." icon={<AlertCircle size={22} className="text-rose-600" />} onClick={() => setActiveTab('emergency')} status="Urgente" />
    </div>

    <div className="grid grid-cols-1 lg:grid-cols-3 gap-8">
      <div className="lg:col-span-2 bg-white border border-slate-200 p-10 rounded-[2.5rem] shadow-sm relative overflow-hidden group transition-all hover:shadow-xl">
        <div className="absolute -top-12 -right-12 w-64 h-64 bg-emerald-50 rounded-full opacity-50 group-hover:scale-110 transition-transform"></div>
        <div className="max-w-2xl space-y-6 relative z-10">
          <div className="flex items-center gap-3"><History size={24} className="text-emerald-600" /><h2 className="text-2xl font-bold italic tracking-tight">Control Operativo 2026</h2></div>
          <p className="text-slate-600 text-lg leading-relaxed">Nuestra firma lidera el mercado en la gestión de mercancías sensibles y de alto valor. Desde el despacho de moda italiana hasta la exportación legal de productos marinos regulados por CITES.</p>
          <div className="flex gap-4">
            <button onClick={() => setActiveTab('clients')} className="bg-[#0F172A] text-white px-10 py-4 rounded-full font-bold hover:scale-105 transition-all flex items-center gap-3 shadow-xl shadow-slate-900/10">Gestionar Cartera <ArrowRightLeft size={18} /></button>
            <button className="bg-white border border-slate-200 px-6 py-4 rounded-full font-bold hover:bg-slate-50 transition-all flex items-center gap-2 text-slate-600"><Download size={18} /> Manual PDF</button>
          </div>
        </div>
      </div>

      <div className="bg-[#0F172A] text-white p-10 rounded-[2.5rem] shadow-2xl flex flex-col justify-between relative overflow-hidden">
        <div className="absolute top-0 right-0 p-8 opacity-10"><ShieldCheck size={120} /></div>
        <div className="space-y-6">
          <h4 className="text-lg font-bold italic border-b border-white/10 pb-4 flex items-center gap-2 text-emerald-400">
            <ShieldCheck size={20} /> Estatus Legal GR&A
          </h4>
          <div className="space-y-4">
            <div className="flex justify-between items-center text-sm border-b border-white/5 pb-2">
              <span className="text-slate-400">Certificación OEA</span>
              <span className="text-emerald-400 font-bold uppercase text-[10px] tracking-widest">Vigente</span>
            </div>
            <div className="flex justify-between items-center text-sm border-b border-white/5 pb-2">
              <span className="text-slate-400">Padrones Sectoriales</span>
              <span className="text-emerald-400 font-bold uppercase text-[10px] tracking-widest">Activos</span>
            </div>
            <div className="flex justify-between items-center text-sm">
              <span className="text-slate-400">Opinión SAT</span>
              <span className="text-emerald-400 font-bold uppercase text-[10px] tracking-widest">Positiva</span>
            </div>
          </div>
        </div>
        <div className="mt-8">
           <div className="bg-white/5 p-4 rounded-2xl border border-white/10 text-center animate-pulse">
             <p className="text-[10px] font-black text-slate-500 uppercase tracking-widest mb-1">VUCE Sync</p>
             <p className="text-sm font-mono text-emerald-400 font-bold">100% ONLINE</p>
           </div>
        </div>
      </div>
    </div>
  </div>
);

const MaxMaraView = ({ onBack }) => {
  const [selectedProduct, setSelectedProduct] = useState(null);

  const productDetails = {
    footwear: {
      name: "Calzado / Zapatos",
      tigie: "6403.51.01.01 (NICO 01)",
      description: "Calzado con suela de cuero natural y parte superior de piel de origen animal.",
      permissions: "Padrón Sectorial de Calzado, Precios Estimados (DOF), NOM-020-SCFI.",
      legal: "Art. 36-A LA (Documentación), Art. 59-IV LA (Padrón Sectorial).",
      process: "Validación estricta de precio unitario contra lista de precios estimados de la SHCP para evitar multas por subvaluación."
    },
    textile_cotton: {
      name: "Prendas de Algodón",
      tigie: "6109.10.01.00 (NICO 01)",
      description: "T-shirts y camisetas de punto de algodón (>50% de fibras naturales).",
      permissions: "Aviso Automático de Importación de Productos Textiles (SE), NOM-004-SE-2021.",
      legal: "LIGIE Sección XI - Notas Explicativas del Sistema Armonizado.",
      process: "Verificación de composición exacta y etiquetado cosido en origen con RFC del importador."
    },
    calfskin: {
      name: "Piel de Ternera",
      tigie: "4202.21.01.01 (NICO 01)",
      description: "Bolsos de mano con superficie exterior de cuero natural curtido en Italia.",
      permissions: "Permiso Sanitario, NOM-020-SCFI (Información comercial en cueros).",
      legal: "Reglas Generales de Comercio Exterior 3.1.28.",
      process: "Certificado de origen de curtiduría italiana. Inspección física previa en puerto."
    },
    wool_coats: {
      name: "Abrigos de Lana",
      tigie: "6202.20.01.00 (NICO 01)",
      description: "Abrigos y chaquetones de lana o pelo fino. Piezas icónicas de colección.",
      permissions: "Padrón Sectorial Textil, Etiquetado NOM-004 vigente.",
      legal: "TLCUEM (Certificado EUR.1 / Declaración en factura para arancel 0%).",
      process: "Aplicación de beneficio arancelario mediante prueba de origen de la Unión Europea."
    }
  };

  return (
    <div className="space-y-8 animate-in slide-in-from-bottom-10 duration-500 pb-20">
      <button onClick={onBack} className="flex items-center gap-2 text-slate-400 hover:text-emerald-600 font-bold uppercase text-[10px] tracking-widest transition-colors"><ArrowRightLeft size={16} className="rotate-180" /> Regresar a Cartera</button>
      
      <div className="bg-white border border-slate-200 p-10 rounded-[3rem] shadow-sm flex flex-col md:flex-row items-center gap-10">
        <div className="w-32 h-32 bg-[#0F172A] text-white rounded-full flex items-center justify-center font-serif text-5xl shadow-2xl shrink-0 ring-8 ring-slate-50">MM</div>
        <div className="flex-1 text-center md:text-left">
          <h2 className="text-5xl font-bold tracking-tighter mb-2 italic underline decoration-emerald-100 decoration-8 underline-offset-8 text-slate-900 font-serif">Max Mara <span className="font-light text-slate-400">Italia</span></h2>
          <p className="text-slate-500 text-xl font-medium tracking-tight">Retail de Lujo | Despacho Aduanero de Alta Precisión</p>
          <div className="flex gap-2 mt-4 justify-center md:justify-start flex-wrap">
            <span className="px-3 py-1 bg-emerald-100 text-emerald-700 rounded-full text-[10px] font-black uppercase tracking-widest">Socio Estratégico</span>
            <span className="px-3 py-1 bg-blue-100 text-blue-700 rounded-full text-[10px] font-black uppercase tracking-widest">Logística White-Glove</span>
          </div>
        </div>
      </div>

      <div className="space-y-6">
        <h3 className="text-3xl font-bold italic border-l-8 border-emerald-500 pl-6 tracking-tight text-slate-800">Catálogo Técnico de Mercancías</h3>
        <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6">
          {Object.entries(productDetails).map(([key, product]) => (
            <button key={key} onClick={() => setSelectedProduct(product)} className={`p-8 rounded-[2.5rem] border-2 text-left transition-all ${selectedProduct?.name === product.name ? 'border-emerald-500 bg-white shadow-xl scale-105' : 'bg-white border-slate-100 shadow-sm hover:border-emerald-200'}`}>
              <div className={`w-12 h-12 rounded-xl flex items-center justify-center mb-6 transition-colors ${selectedProduct?.name === product.name ? 'bg-emerald-500 text-white' : 'bg-slate-50 text-slate-900 border border-slate-100'}`}>
                <Package size={22} />
              </div>
              <h4 className="text-xl font-bold mb-2 italic text-slate-800 tracking-tight">{product.name}</h4>
              <p className="text-[10px] font-black text-slate-400 uppercase tracking-widest text-xs">TIGIE: {product.tigie}</p>
            </button>
          ))}
        </div>

        {selectedProduct && (
          <div className="bg-white border-2 border-emerald-500 p-10 rounded-[3rem] shadow-2xl animate-in zoom-in duration-300 relative mt-8">
            <button onClick={() => setSelectedProduct(null)} className="absolute top-6 right-6 p-2 hover:bg-slate-100 rounded-full transition-colors text-slate-400 hover:text-emerald-500"><X size={24} /></button>
            <div className="grid grid-cols-1 md:grid-cols-2 gap-10">
              <div className="space-y-6">
                <div>
                  <h4 className="text-3xl font-black italic underline decoration-emerald-100 underline-offset-8 text-slate-900">{selectedProduct.name}</h4>
                  <p className="text-slate-600 font-medium leading-relaxed mt-2">{selectedProduct.description}</p>
                </div>
                <div className="space-y-4">
                  <div className="p-6 bg-slate-50 rounded-2xl border border-slate-100 hover:shadow-inner transition-all">
                    <p className="text-[10px] font-black text-slate-400 uppercase mb-2 flex items-center gap-2"><Gavel size={14} className="text-emerald-500" /> Fundamento Legal</p>
                    <p className="text-sm font-bold text-slate-800 italic">{selectedProduct.legal}</p>
                  </div>
                  <div className="p-6 bg-emerald-50 rounded-2xl border border-emerald-100">
                    <p className="text-[10px] font-black text-emerald-600 uppercase mb-2 flex items-center gap-2"><ShieldCheck size={14} /> Permisos & RRNAs</p>
                    <p className="text-sm font-bold text-emerald-900 leading-relaxed uppercase text-xs">{selectedProduct.permissions}</p>
                  </div>
                </div>
              </div>
              <div className="p-8 bg-[#0F172A] text-white rounded-[2rem] shadow-xl space-y-6 flex flex-col justify-center">
                <div className="flex items-center gap-3">
                  <div className="p-2 bg-emerald-500 rounded-lg"><ClipboardCheck size={20} /></div>
                  <h5 className="font-black text-xs uppercase tracking-[0.2em] text-emerald-400">Protocolo Operativo GR&A</h5>
                </div>
                <p className="text-sm text-slate-300 italic leading-relaxed border-l-2 border-emerald-500 pl-4">
                  {selectedProduct.process}
                </p>
                <div className="pt-4 border-t border-white/10">
                  <p className="text-[10px] font-bold text-slate-500 uppercase tracking-widest italic">Responsable de Clasificación: Área Técnica</p>
                </div>
              </div>
            </div>
          </div>
        )}
      </div>

      <div className="bg-white border border-slate-200 p-10 rounded-[3rem] shadow-sm space-y-8">
        <h3 className="text-2xl font-bold italic border-l-8 border-[#0F172A] pl-6 tracking-tight text-slate-800 flex items-center gap-3 underline decoration-slate-100 decoration-8 underline-offset-8"><Truck /> Flujo de Despacho Integral</h3>
        <div className="space-y-6">
          <StepItem num="1" title="Arribo y Pre-Alerta Digital" content="Recepción de documentos de Italia. Digitalización en VUCE conforme al Art. 36-A LA. Generación de expediente electrónico preventivo." />
          <StepItem num="2" title="Reconocimiento Previo Estratégico" content="Inspección en recinto fiscal para validar composición textil, marcas y cumplimiento estricto de la etiqueta NOM-004." />
          <StepItem num="3" title="Determinación TIGIE & NICOs" content="Clasificación arancelaria final 2026. Pago de contribuciones (IGI, IVA, DTA) vía PECE (Art. 83 LA)." />
          <StepItem num="4" title="Semáforo Fiscal (Art. 43 LA)" content="Activación del mecanismo automatizado. Gestión legal in-situ en caso de incidencia o reconocimiento aduanero." />
          <StepItem num="5" title="Entrega de Última Milla Boutique" content="Carga en camiones blindados con GPS. Entrega directa en boutique (Antara, Santa Fe, Polanco) con acuse digital (POD)." />
        </div>
      </div>
    </div>
  );
};

const BuchePescadoView = ({ onBack }) => {
  const [selectedSpec, setSelectedSpec] = useState(null);

  const regulatoryInfo = {
    cites: {
      title: "Certificación CITES",
      desc: "Tratado internacional para asegurar que el comercio no amenace la supervivencia de las especies.",
      legal: "Ley General de Vida Silvestre / Apéndices CITES México.",
      requirements: "Permiso de exportación emitido por SEMARNAT tras validación de origen legal y biológico."
    },
    senasica: {
      title: "Certificado Zoosanitario",
      desc: "Validación de inocuidad y cumplimiento sanitario animal para exportación de productos del mar.",
      legal: "Ley Federal de Sanidad Animal / NOMs de Salud.",
      requirements: "Certificado CZE emitido por SENASICA tras inspección física del producto y almacén."
    },
    profepa: {
      title: "Inspección PROFEPA",
      desc: "Inspección ocular física obligatoria en punto de despacho para validar que el Buche no sea de especies prohibidas.",
      legal: "NOM-059-SEMARNAT (Protección de especies en peligro).",
      requirements: "Acta de inspección ocular, validación de sellos de seguridad y conteo físico por pieza."
    }
  };

  return (
    <div className="space-y-8 animate-in slide-in-from-right-10 duration-500 pb-20">
      <button onClick={onBack} className="flex items-center gap-2 text-slate-400 hover:text-emerald-600 font-bold uppercase text-[10px] tracking-widest transition-colors"><ArrowRightLeft size={16} className="rotate-180" /> Regresar a Cartera</button>
      
      <div className="bg-white border border-slate-200 p-10 rounded-[3rem] shadow-sm flex flex-col md:flex-row items-center gap-10">
        <div className="w-32 h-32 bg-emerald-600 text-white rounded-full flex items-center justify-center font-serif text-5xl shadow-2xl shrink-0 border-8 border-emerald-50"><Fish size={54} /></div>
        <div className="flex-1 text-center md:text-left">
          <h2 className="text-5xl font-bold tracking-tighter mb-2 italic underline decoration-emerald-100 decoration-8 underline-offset-8 text-slate-900">Buche de Pescado <span className="font-light text-slate-400 text-3xl">(Maw)</span></h2>
          <p className="text-slate-500 text-xl font-medium tracking-tight">Exportación Estratégica | Mercancía Crítica de Alta Regulación</p>
          <div className="flex gap-2 mt-4 justify-center md:justify-start">
            <span className="px-3 py-1 bg-rose-100 text-rose-700 rounded-full text-[10px] font-black uppercase tracking-widest flex items-center gap-2"><AlertCircle size={10} /> Mercancía Sensible</span>
          </div>
        </div>
      </div>

      <div className="grid grid-cols-1 md:grid-cols-3 gap-6">
        <div className="p-8 bg-white border border-slate-100 rounded-[2rem] shadow-sm group hover:border-emerald-500 transition-all">
          <h4 className="text-[10px] font-black text-slate-400 uppercase tracking-widest mb-2">Fracción TIGIE 2026</h4>
          <p className="text-3xl font-black font-mono text-slate-900 tracking-tight">0305.72.01.00</p>
          <p className="text-[10px] text-slate-400 italic mt-2">Vejigas natatorias de pescados.</p>
        </div>
        <div className="p-8 bg-white border border-slate-100 rounded-[2rem] shadow-sm group hover:border-emerald-500 transition-all text-center">
          <h4 className="text-[10px] font-black text-slate-400 uppercase tracking-widest mb-2">Identificador NICO</h4>
          <p className="text-3xl font-black font-mono text-emerald-600">00</p>
          <p className="text-[10px] text-slate-400 italic mt-2">NICO Estándar Pesca</p>
        </div>
        <div className="p-8 bg-[#0F172A] text-white rounded-[2rem] shadow-xl">
          <h4 className="text-[10px] font-black text-emerald-400 uppercase tracking-widest mb-2 font-mono tracking-widest">Estatus Legal</h4>
          <p className="text-2xl font-black italic">Apta Exportación</p>
          <p className="text-[10px] text-slate-500 mt-2">Pre-inspección GR&A aprobada.</p>
        </div>
      </div>

      <div className="space-y-6">
        <h3 className="text-3xl font-bold italic border-l-8 border-emerald-600 pl-6 tracking-tight text-slate-800">Regulaciones Críticas & Blindaje Legal</h3>
        <div className="grid grid-cols-1 md:grid-cols-3 gap-6">
          {Object.entries(regulatoryInfo).map(([key, info]) => (
            <button key={key} onClick={() => setSelectedSpec(info)} className={`bg-white p-8 rounded-[2rem] border-2 text-left transition-all group shadow-sm ${selectedSpec?.title === info.title ? 'border-emerald-600' : 'border-slate-100 hover:border-emerald-200'}`}>
              <div className={`w-12 h-12 rounded-xl flex items-center justify-center mb-6 transition-colors ${selectedSpec?.title === info.title ? 'bg-emerald-600 text-white shadow-lg' : 'bg-slate-50 text-slate-900 border border-slate-100 group-hover:bg-emerald-50'}`}>
                <ShieldCheck size={24} />
              </div>
              <h4 className="text-xl font-bold mb-2 italic text-slate-800">{info.title}</h4>
              <p className="text-[10px] text-slate-400 font-black uppercase tracking-tighter">Consultar Base Jurídica</p>
            </button>
          ))}
        </div>

        {selectedSpec && (
          <div className="bg-white border-2 border-emerald-600 p-10 rounded-[3rem] shadow-2xl animate-in zoom-in duration-300 relative">
            <button onClick={() => setSelectedSpec(null)} className="absolute top-6 right-6 p-2 hover:bg-slate-100 rounded-full transition-colors text-slate-400 hover:text-emerald-500"><X size={24} /></button>
            <div className="grid grid-cols-1 md:grid-cols-2 gap-10">
              <div className="space-y-4">
                <h4 className="text-3xl font-black italic underline decoration-emerald-100 underline-offset-8 text-slate-900">{selectedSpec.title}</h4>
                <p className="text-slate-600 font-medium leading-relaxed italic">{selectedSpec.desc}</p>
                <div className="p-6 bg-emerald-50 rounded-2xl border border-emerald-100">
                  <p className="text-[10px] font-black text-emerald-600 uppercase mb-2">Base Jurídica Nacional</p>
                  <p className="text-sm font-bold text-emerald-900 italic font-serif">"{selectedSpec.legal}"</p>
                </div>
              </div>
              <div className="p-8 bg-[#0F172A] text-white rounded-[2rem] shadow-xl flex flex-col justify-center border-l-8 border-emerald-500">
                <h5 className="font-black text-xs uppercase tracking-widest text-emerald-400 mb-4 tracking-[0.2em] flex items-center gap-2 underline decoration-emerald-500/20">
                  <ClipboardCheck size={18} /> Obligaciones en Aduana
                </h5>
                <p className="text-sm text-slate-300 italic leading-relaxed">{selectedSpec.requirements}</p>
                <div className="mt-6 flex items-center gap-3 p-4 bg-white/5 rounded-xl border border-white/5">
                  <AlertCircle className="text-rose-400 shrink-0" size={20} />
                  <p className="text-[10px] font-black text-rose-300 uppercase italic leading-tight">La omisión de este documento genera embargo precautorio inmediato.</p>
                </div>
              </div>
            </div>
          </div>
        )}
      </div>
    </div>
  );
};

const ClientsGeneralView = ({ clients, onSelect, onAdd }) => (
  <div className="space-y-8 animate-in fade-in duration-500">
    <div className="flex justify-between items-center bg-white p-8 rounded-[2rem] shadow-sm border border-slate-100">
      <div>
        <h2 className="text-3xl font-bold tracking-tight italic border-b-4 border-[#0F172A] inline-block uppercase tracking-tighter text-slate-900">Cartera de Clientes</h2>
        <p className="text-slate-500 text-sm mt-2 font-medium italic underline decoration-slate-100 underline-offset-4">Gestión y Fichas Técnicas González Robles & Asociados</p>
      </div>
      <button onClick={onAdd} className="bg-[#0F172A] text-white px-8 py-3 rounded-full font-black text-xs uppercase tracking-widest shadow-lg flex items-center gap-2 hover:scale-105 transition-all hover:bg-emerald-600">
        <Plus size={18} /> Nuevo Socio Comercial
      </button>
    </div>

    <div className="bg-white border border-slate-200 rounded-[2.5rem] overflow-hidden shadow-xl shadow-slate-200/50 relative">
      <table className="w-full text-left">
        <thead className="bg-slate-50 border-b border-slate-200">
          <tr>
            <th className="p-6 text-[10px] font-black uppercase text-slate-400 tracking-widest">Socio / Empresa</th>
            <th className="p-6 text-[10px] font-black uppercase text-slate-400 tracking-widest">Sector Económico</th>
            <th className="p-6 text-[10px] font-black uppercase text-slate-400 tracking-widest">Estatus</th>
            <th className="p-6 text-[10px] font-black uppercase text-slate-400 tracking-widest">Prioridad</th>
            <th className="p-6 text-[10px] font-black uppercase text-slate-400 tracking-widest text-center">Ficha Técnica</th>
          </tr>
        </thead>
        <tbody className="divide-y divide-slate-100">
          {clients.map((c) => (
            <tr key={c.id} className="hover:bg-slate-50/50 transition-colors group">
              <td className="p-6">
                <div className="flex items-center gap-4">
                  <div className="w-12 h-12 bg-slate-900 text-white rounded-2xl flex items-center justify-center font-bold text-xs group-hover:bg-emerald-600 transition-colors shadow-lg shadow-slate-900/10">{c.icon}</div>
                  <span className="font-black text-slate-800 italic text-lg tracking-tight group-hover:translate-x-1 transition-transform">{c.name}</span>
                </div>
              </td>
              <td className="p-6 text-xs font-bold text-slate-500 italic tracking-tight uppercase">{c.sector}</td>
              <td className="p-6 text-sm">
                <span className={`px-4 py-1 rounded-full text-[10px] font-black uppercase tracking-widest ${c.status === 'Activo' ? 'bg-emerald-100 text-emerald-700' : 'bg-amber-100 text-amber-700'}`}>{c.status}</span>
              </td>
              <td className="p-6 text-xs font-black italic text-slate-600">{c.priority}</td>
              <td className="p-6 text-center">
                <button onClick={() => onSelect(c)} className="p-3 bg-[#0F172A] text-white rounded-xl hover:bg-emerald-600 transition-all shadow-md inline-flex items-center justify-center group-hover:scale-110">
                  <Eye size={20} />
                </button>
              </td>
            </tr>
          ))}
        </tbody>
      </table>
    </div>
  </div>
);

const ClientDetailView = ({ client, onBack }) => {
  if (!client) return null;
  return (
    <div className="space-y-8 animate-in slide-in-from-right-10 duration-500 pb-20">
      <button onClick={onBack} className="flex items-center gap-2 text-slate-400 hover:text-emerald-600 font-bold uppercase text-[10px] tracking-widest transition-colors"><ArrowRightLeft size={16} className="rotate-180" /> Volver a Cartera</button>
      <div className="bg-white border border-slate-200 p-10 rounded-[3rem] shadow-sm flex flex-col md:flex-row items-center gap-10">
        <div className="w-32 h-32 bg-[#0F172A] text-white rounded-full flex items-center justify-center font-serif text-5xl shadow-2xl shrink-0 ring-8 ring-slate-50">{client.icon}</div>
        <div className="flex-1 text-center md:text-left">
          <h2 className="text-5xl font-bold tracking-tighter mb-2 italic underline decoration-slate-100 decoration-8 underline-offset-8 text-slate-900 font-serif">{client.name}</h2>
          <p className="text-slate-500 text-xl font-medium tracking-tight">{client.sector}</p>
          <p className="mt-4 text-slate-400 text-sm max-w-2xl italic leading-relaxed font-medium uppercase tracking-tight">{client.info}</p>
        </div>
      </div>
      <div className="grid grid-cols-1 md:grid-cols-2 gap-8">
        <div className="p-10 bg-white border border-slate-200 rounded-[2.5rem] shadow-sm space-y-6">
          <h3 className="font-bold text-xl italic border-b border-slate-100 pb-4 text-slate-800 flex items-center gap-2 uppercase tracking-tighter">
            <Package className="text-emerald-600" /> Información de Operación
          </h3>
          <div className="space-y-2">
            <InfoRow label="Estatus Operativo" value={client.status} />
            <InfoRow label="Nivel de Prioridad" value={client.priority} />
            <InfoRow label="Socio ID" value={client.id} />
            <InfoRow label="Actividad 2026" value="Consultoría Técnica" />
          </div>
        </div>
        <div className="p-10 bg-[#0F172A] text-white rounded-[2.5rem] shadow-2xl flex flex-col items-center justify-center text-center gap-4 border border-white/5">
          <div className="p-4 bg-white/5 rounded-full"><Settings className="text-emerald-400" size={32} /></div>
          <p className="text-slate-400 text-sm italic tracking-tight leading-relaxed max-w-xs uppercase font-black text-xs">Módulo de documentación aduanera avanzada en desarrollo para esta cuenta.</p>
        </div>
      </div>
    </div>
  );
};

const AddClientModal = ({ onAdd, onClose }) => {
  const [formData, setFormData] = useState({ name: '', sector: '', status: 'Activo', priority: 'Media', info: '' });
  return (
    <div className="fixed inset-0 bg-slate-900/80 backdrop-blur-md z-50 flex items-center justify-center p-4">
      <div className="bg-white w-full max-w-xl rounded-[3rem] shadow-2xl overflow-hidden animate-in zoom-in duration-300 border border-slate-200">
        <div className="p-10 border-b border-slate-100 flex justify-between items-center bg-slate-50">
          <div><h2 className="text-3xl font-bold italic tracking-tighter text-slate-900">Alta de <span className="font-black text-emerald-600">Cliente</span></h2><p className="text-[10px] font-bold text-slate-400 uppercase tracking-widest font-black">González Robles & Asociados</p></div>
          <button onClick={onClose} className="p-2 hover:bg-white rounded-full transition-colors text-slate-400 hover:text-rose-500 shadow-sm"><X size={24} /></button>
        </div>
        <form className="p-10 space-y-6" onSubmit={(e) => { e.preventDefault(); onAdd(formData); }}>
          <div className="grid grid-cols-2 gap-6">
            <div className="space-y-1"><label className="text-[10px] font-black uppercase text-slate-400 tracking-widest ml-1">Nombre Comercial</label><input required className="w-full p-4 bg-slate-50 border border-slate-200 rounded-2xl outline-none focus:ring-2 focus:ring-emerald-500 transition-all font-bold italic text-slate-700 shadow-inner" value={formData.name} onChange={e => setFormData({...formData, name: e.target.value})} /></div>
            <div className="space-y-1"><label className="text-[10px] font-black uppercase text-slate-400 tracking-widest ml-1">Sector</label><input required className="w-full p-4 bg-slate-50 border border-slate-200 rounded-2xl outline-none focus:ring-2 focus:ring-emerald-500 transition-all font-bold italic text-slate-700 shadow-inner" value={formData.sector} onChange={e => setFormData({...formData, sector: e.target.value})} /></div>
          </div>
          <div className="space-y-1"><label className="text-[10px] font-black uppercase text-slate-400 tracking-widest ml-1">Descripción de Operativa</label><textarea className="w-full p-4 bg-slate-50 border border-slate-200 rounded-2xl outline-none h-28 focus:ring-2 focus:ring-emerald-500 transition-all font-bold italic text-slate-700 shadow-inner resize-none" value={formData.info} onChange={e => setFormData({...formData, info: e.target.value})}></textarea></div>
          <button type="submit" className="w-full bg-[#0F172A] text-white p-5 rounded-2xl font-bold hover:shadow-2xl transition-all uppercase tracking-widest text-xs hover:bg-emerald-600 shadow-lg shadow-slate-900/10">Registrar en Cartera Corporativa</button>
        </form>
      </div>
    </div>
  );
};

// --- COMPONENTES COMPARTIDOS ---

const KPIBoxSmall = ({ label, value, color }) => {
  const colorMap = {
    blue: 'text-blue-600',
    emerald: 'text-emerald-600',
    rose: 'text-rose-600',
    amber: 'text-amber-600'
  };
  return (
    <div className="bg-white border border-slate-200 px-8 py-5 rounded-[2rem] shadow-sm flex flex-col items-center hover:shadow-md transition-shadow">
      <p className="text-[10px] font-black text-slate-400 uppercase tracking-[0.2em] mb-1">{label}</p>
      <p className={`text-3xl font-black italic tracking-tighter ${colorMap[color] || 'text-slate-900'}`}>{value}</p>
    </div>
  );
};

const Card = ({ title, desc, icon, onClick, status }) => (
  <button onClick={onClick} className="bg-white p-8 rounded-[2.5rem] border border-slate-100 text-left hover:shadow-2xl hover:border-emerald-500 transition-all group relative overflow-hidden shadow-sm">
    <div className="absolute top-4 right-6 text-[8px] font-black uppercase text-slate-300 group-hover:text-emerald-600 tracking-widest transition-colors">{status}</div>
    <div className="p-4 bg-slate-50 rounded-2xl w-fit mb-8 shadow-inner border border-slate-100 group-hover:bg-emerald-50 transition-colors">{icon}</div>
    <h3 className="text-xl font-black mb-1 italic underline decoration-slate-100 group-hover:decoration-emerald-100 transition-all text-slate-800 tracking-tight">{title}</h3>
    <p className="text-slate-400 text-[10px] leading-relaxed uppercase font-bold tracking-widest">{desc}</p>
  </button>
);

const StepItem = ({ num, title, content }) => (
  <div className="flex gap-8 group">
    <div className="w-12 h-12 rounded-full bg-[#0F172A] text-white flex items-center justify-center font-black shrink-0 shadow-xl shadow-slate-900/10 group-hover:scale-110 group-hover:bg-emerald-600 transition-all border-4 border-slate-50">{num}</div>
    <div className="flex-1 pb-8 border-b border-slate-100 last:border-0">
      <h4 className="font-bold italic text-xl mb-1 text-slate-800 tracking-tight group-hover:translate-x-1 transition-transform">{title}</h4>
      <p className="text-sm text-slate-500 font-medium leading-relaxed italic">{content}</p>
    </div>
  </div>
);

const InfoRow = ({ label, value }) => (
  <div className="flex justify-between items-center py-3 border-b border-slate-50 last:border-0">
    <span className="text-[10px] font-black text-slate-400 uppercase tracking-widest">{label}</span>
    <span className="text-sm font-bold text-slate-800 italic underline decoration-slate-100 underline-offset-4">{value}</span>
  </div>
);

const SearchLoader = () => (
  <div className="bg-white p-10 rounded-[3rem] border border-emerald-200 shadow-2xl flex items-center justify-center gap-6 animate-pulse">
    <div className="p-3 bg-emerald-50 rounded-full"><Loader2 className="animate-spin text-emerald-600" size={32} /></div>
    <div className="space-y-1">
      <p className="font-black text-slate-800 italic text-lg tracking-tight">González Robles & Asociados Intelligence</p>
      <p className="text-xs text-slate-400 uppercase tracking-widest font-bold">Consultando bases de datos internacionales 2026...</p>
    </div>
  </div>
);

const SearchResults = ({ results, onClose }) => (
  <div className="bg-white p-10 rounded-[3rem] border border-slate-200 shadow-2xl relative animate-in zoom-in duration-300 border-t-8 border-t-emerald-600 overflow-hidden">
    <div className="absolute top-0 right-0 p-12 opacity-5 pointer-events-none"><BookOpen size={180} /></div>
    <button onClick={onClose} className="absolute top-6 right-6 p-2 bg-slate-50 text-slate-400 hover:text-rose-500 rounded-full transition-all shadow-sm"><X size={20} /></button>
    <div className="flex items-center gap-3 mb-6 text-emerald-600 font-black uppercase tracking-[0.2em] text-xs">
      <div className="p-1.5 bg-emerald-100 rounded-lg"><Globe size={18} /></div>
      Resultado de Inteligencia Aduanera
    </div>
    <div className="text-sm leading-relaxed whitespace-pre-line mb-8 italic text-slate-700 font-medium pr-12 relative z-10 max-h-[400px] overflow-y-auto custom-scrollbar">
      {results.text}
    </div>
    {results.sources && results.sources.length > 0 && (
      <div className="border-t border-slate-100 pt-6 relative z-10">
        <p className="text-[10px] font-black text-slate-400 uppercase mb-4 tracking-widest ml-1">Fuentes Técnicas Consultadas:</p>
        <div className="flex flex-wrap gap-2">
          {results.sources.map((s, i) => (
            <a key={i} href={s.uri} target="_blank" rel="noreferrer" className="flex items-center gap-2 text-[10px] text-emerald-700 bg-emerald-50 border border-emerald-100 px-3 py-1.5 rounded-full font-bold hover:bg-emerald-600 hover:text-white transition-all shadow-sm uppercase tracking-tight">
              {s.title} <ExternalLink size={10} />
            </a>
          ))}
        </div>
      </div>
    )}
  </div>
);

// --- VISTAS TÉCNICAS ESTÁTICAS ---

const LigieView = () => (
  <div className="space-y-8 animate-in fade-in duration-500">
    <div className="bg-white p-8 rounded-[2rem] border border-slate-100 shadow-sm">
      <h2 className="text-3xl font-bold italic border-b-4 border-[#0F172A] inline-block tracking-tighter text-slate-900 uppercase">Catálogo LIGIE 2026</h2>
      <p className="text-slate-500 text-sm mt-2 italic font-medium underline decoration-slate-100 underline-offset-4 tracking-tight">Sincronización con la Séptima Enmienda del Sistema Armonizado</p>
    </div>
    <div className="grid grid-cols-1 md:grid-cols-2 gap-8">
      <div className="p-10 bg-white border border-slate-100 rounded-[2.5rem] shadow-xl relative overflow-hidden group hover:border-emerald-500 transition-all">
        <div className="absolute -bottom-8 -right-8 opacity-5 group-hover:scale-110 transition-transform"><BookOpen size={160} /></div>
        <h4 className="font-black text-xs uppercase tracking-[0.2em] mb-8 flex items-center gap-2 text-emerald-600"><div className="w-2 h-2 bg-emerald-500 rounded-full animate-pulse"></div> Estructura Arancelaria</h4> 
        <div className="space-y-6"> 
          <div className="flex items-center gap-5"> 
            <div className="w-14 h-14 bg-[#0F172A] text-white flex items-center justify-center font-mono font-bold rounded-2xl shadow-xl shadow-slate-900/20">61</div> 
            <div className="space-y-0.5"><p className="text-sm font-bold italic text-slate-800 underline decoration-slate-100 underline-offset-2">Capítulo Técnico</p><p className="text-[10px] text-slate-400 font-bold uppercase tracking-widest">Ej: Prendas de Punto</p></div> 
          </div> 
          <div className="flex items-center gap-5"> 
            <div className="w-14 h-14 bg-emerald-600 text-white flex items-center justify-center font-mono font-bold rounded-2xl shadow-xl shadow-emerald-600/20 underline">01</div> 
            <div className="space-y-0.5"><p className="text-sm font-bold italic text-slate-800 underline decoration-slate-100 underline-offset-2">Fracción Arancelaria</p><p className="text-[10px] text-slate-400 font-bold uppercase tracking-widest">Base Impositiva IGI</p></div> 
          </div> 
          <div className="flex items-center gap-5"> 
            <div className="w-14 h-14 bg-slate-900 text-white flex items-center justify-center font-mono font-bold rounded-2xl shadow-xl shadow-slate-900/20 border-2 border-emerald-400">00</div> 
            <div className="space-y-0.5"><p className="text-sm font-bold italic text-slate-800 underline decoration-emerald-50 underline-offset-2">Identificador NICO</p><p className="text-[10px] text-emerald-600 font-black uppercase tracking-[0.2em]">Data Estadística 2026</p></div> 
          </div> 
        </div> 
      </div> 
      <div className="p-10 bg-[#0F172A] text-white rounded-[2.5rem] shadow-2xl flex flex-col justify-center space-y-8 relative overflow-hidden"> 
        <div className="absolute top-0 right-0 p-8 opacity-10"><Scale size={120} /></div>
        <div className="space-y-2">
          <h4 className="text-2xl font-bold italic border-b border-white/10 pb-4 tracking-tight text-emerald-400 flex items-center gap-3"><ShieldCheck size={24} /> Blindaje LIGIE</h4> 
          <p className="text-slate-400 text-sm leading-relaxed italic pr-12">"La actualización 2026 prioriza la trazabilidad en fibras textiles recicladas y productos de origen animal regulados, reduciendo la ambigüedad en la clasificación técnica."</p> 
        </div>
        <button className="flex items-center gap-3 bg-white text-slate-900 px-6 py-3 rounded-full font-black text-[10px] uppercase tracking-widest hover:bg-emerald-500 hover:text-white transition-all w-fit shadow-xl shadow-white/5">Ver Notas Explicativas <ExternalLink size={14} /></button>
      </div> 
    </div>
  </div>
);

const LegalFrameworkView = () => (
  <div className="space-y-8 animate-in fade-in duration-500">
    <div className="bg-white p-8 rounded-[2rem] border border-slate-100 shadow-sm border-l-8 border-l-[#0F172A]">
      <h2 className="text-3xl font-bold italic tracking-tighter text-slate-900 uppercase">Marco Jurídico Aduanero</h2>
      <p className="text-slate-500 text-sm mt-1 italic font-medium uppercase tracking-widest">Base Legal para Operaciones González Robles & Asociados</p>
    </div>
    <div className="grid grid-cols-1 md:grid-cols-3 gap-6"> 
      <LegalCard title="Art. 36-A LA" subtitle="Documentación Digital" desc="Obligación de transmitir documentos electrónicos (e-documents) relativos al valor y cumplimiento de RRNAs." /> 
      <LegalCard title="Art. 54 LA" subtitle="Responsabilidad Técnica" desc="Define la responsabilidad solidaria del Agente Aduanal sobre la veracidad de datos y clasificación arancelaria." /> 
      <LegalCard title="RGCE 2026" subtitle="Reglas de Comercio" desc="Normativas vigentes para el despacho, padrones sectoriales y facilidades administrativas en el despacho de lujo." /> 
    </div>
    <div className="p-10 bg-white border border-slate-200 rounded-[3rem] shadow-sm flex flex-col md:flex-row items-center gap-10 hover:shadow-xl transition-all group border-b-8 border-b-emerald-500">
      <div className="w-24 h-24 bg-slate-50 rounded-full flex items-center justify-center text-slate-900 group-hover:bg-[#0F172A] group-hover:text-white transition-all shadow-inner"><Gavel size={40} /></div>
      <div className="space-y-3 flex-1">
        <h4 className="text-2xl font-black italic tracking-tight text-slate-900 underline decoration-slate-100 underline-offset-8">Aviso Preventivo Art. 144 LA</h4>
        <p className="text-slate-500 text-sm leading-relaxed font-medium italic">"González Robles & Asociados ejecuta auditorías preventivas constantes para asegurar que el pago de contribuciones sea exacto y auditable en cualquier momento por la autoridad hacendaria."</p>
      </div>
    </div>
  </div>
);

const EmergencyView = () => (
  <div className="space-y-8 animate-in fade-in duration-500">
    <div className="bg-rose-50 p-8 rounded-[2rem] border border-rose-100 border-l-8 border-l-rose-600">
      <h2 className="text-3xl font-bold text-rose-600 italic tracking-tighter uppercase">Protocolos de Respuesta SOS | GR&A</h2>
      <p className="text-rose-400 text-[10px] font-black uppercase tracking-widest mt-1">Línea Crítica para Incidencias en Aduana</p>
    </div>
    <div className="grid grid-cols-1 md:grid-cols-2 gap-8"> 
      <div className="p-10 bg-rose-600 text-white rounded-[3rem] shadow-2xl relative overflow-hidden border-b-8 border-b-rose-800 group hover:scale-[1.01] transition-transform"> 
        <div className="absolute -top-10 -right-10 p-12 opacity-10 group-hover:rotate-12 transition-transform"><AlertCircle size={180} /></div>
        <h3 className="text-2xl font-bold italic border-b border-white/20 pb-6 mb-8 tracking-tight uppercase flex items-center gap-3"><AlertCircle /> Contingencias en Despacho</h3> 
        <p className="text-sm leading-relaxed mb-8 italic font-bold text-rose-100 pr-10">Cualquier discrepancia técnica genera riesgo de PAMA (Art. 150 LA), especialmente en textiles y vida silvestre. La defensa debe ser inmediata y técnica.</p> 
        <div className="space-y-4 relative z-10"> 
          <div className="flex gap-4 items-center bg-white/10 p-5 rounded-2xl border border-white/10 backdrop-blur-sm"> 
            <div className="w-10 h-10 bg-white text-rose-600 flex items-center justify-center rounded-full font-black text-xs shadow-xl tracking-tighter">01</div> 
            <p className="text-[10px] font-black uppercase tracking-widest italic">Movilización Legal In-Situ GR&A</p> 
          </div> 
          <div className="flex gap-4 items-center bg-white/10 p-5 rounded-2xl border border-white/10 backdrop-blur-sm"> 
            <div className="w-10 h-10 bg-white text-rose-600 flex items-center justify-center rounded-full font-black text-xs shadow-xl tracking-tighter">02</div> 
            <p className="text-[10px] font-black uppercase tracking-widest italic">Pruebas Técnicas de Composición</p> 
          </div> 
        </div> 
      </div> 
      <div className="p-10 bg-white border border-slate-200 rounded-[3rem] space-y-8 shadow-xl shadow-slate-200/50 flex flex-col justify-center relative"> 
        <div className="absolute top-6 right-8 text-[8px] font-black text-slate-300 uppercase tracking-[0.3em]">Directorio SOS</div>
        <h3 className="text-xl font-bold italic underline decoration-rose-200 italic tracking-tight underline-offset-8 text-slate-800 uppercase">Línea de Respuesta Inmediata</h3> 
        <div className="space-y-4"> 
          <ContactItem name="Defensa Jurídica Aduanera" tel="+52 55 1234 5678" role="Coordinación PAMA" /> 
          <ContactItem name="Monitoreo Unidades VIP" tel="01-800-TRACK" role="Seguridad Logística" /> 
          <ContactItem name="Enlace PROFEPA / Pesca" tel="01-800-FAUNA" role="Vida Silvestre" /> 
        </div> 
      </div> 
    </div>
  </div>
);

// --- COMPONENTES AUXILIARES ---

const LegalCard = ({ title, subtitle, desc }) => (
  <div className="bg-white p-8 rounded-[2.5rem] border border-slate-100 shadow-sm hover:shadow-2xl hover:border-emerald-500 transition-all group flex flex-col justify-between h-full">
    <div className="space-y-2">
      <div className="px-3 py-1 bg-slate-900 text-white rounded-lg text-[10px] font-black w-fit mb-4 group-hover:bg-emerald-600 transition-colors tracking-widest">{title}</div>
      <h4 className="text-xl font-bold italic text-slate-800 group-hover:text-emerald-600 transition-colors tracking-tight">{subtitle}</h4>
      <p className="text-slate-500 text-xs leading-relaxed font-medium italic">{desc}</p>
    </div>
    <div className="mt-6 flex items-center gap-2 text-slate-300 group-hover:text-emerald-500 transition-colors">
      <span className="text-[8px] font-black uppercase tracking-widest">Consulta Completa</span>
      <ChevronRight size={12} />
    </div>
  </div>
);

const ContactItem = ({ name, tel, role }) => (
  <div className="flex justify-between items-center p-5 bg-slate-50 rounded-2xl border border-slate-100 group hover:border-emerald-500 hover:bg-white transition-all shadow-sm">
    <div className="space-y-1">
      <p className="font-bold text-slate-800 text-xs italic tracking-tight underline decoration-slate-200 group-hover:decoration-emerald-200 underline-offset-2">{name}</p>
      <p className="text-[8px] font-black text-slate-400 uppercase tracking-widest group-hover:text-emerald-500 transition-colors">{role}</p>
    </div>
    <button className="bg-[#0F172A] text-white px-5 py-2.5 rounded-xl text-[10px] font-bold shadow-lg flex items-center gap-2 hover:scale-105 transition-all active:scale-95">
      <PhoneCall size={12} /> Llamar
    </button>
  </div>
);

export default App;
