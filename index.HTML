import React, { useEffect, useMemo, useRef, useState } from "react";

// ==========================================================
// NOTE: Save this file as UTF-8 WITHOUT BOM to avoid
//        "SyntaxError: /: Unexpected token (1:0)" in some parsers.
//        This component replaces the previous raw HTML so it
//        renders correctly in a React environment.
// ==========================================================

export default function MealPlanApp() {
  // ---------- Assets from repo (relative paths) ----------
  const defaultBgPath = "hq720.jpg"; // Kinich background from repo
  const meguminPath = "file_000000007d5061f88ad03e2950b2c2ea.png"; // Megumin image from repo
  const defaultAudioFileName = "Miguel Maintel - rutina-epica 2025-08-20 04_36.m4a"; // from repo

  // Use encodeURI to safely reference filenames with spaces/accents
  const defaultAudioSrc = useMemo(() => encodeURI(defaultAudioFileName), []);

  // ---------- State ----------
  const [bgUrl, setBgUrl] = useState<string>(defaultBgPath);
  const [audioSrc, setAudioSrc] = useState<string>(defaultAudioSrc);
  const audioRef = useRef<HTMLAudioElement | null>(null);

  // ---------- Effects ----------
  useEffect(() => {
    document.title = "QUE SE DESAPAREZCA ESTÁ MRD# XD";
  }, []);

  // Restore saved notes on mount (values are read directly per textarea via defaultValue)

  // ---------- Handlers ----------
  const onBgFileChange = (e: React.ChangeEvent<HTMLInputElement>) => {
    const file = e.target.files && e.target.files[0];
    if (!file) return;
    const reader = new FileReader();
    reader.onload = (ev) => {
      const result = typeof ev.target?.result === "string" ? ev.target?.result : "";
      // Try to persist custom background (can fail if too large for localStorage)
      try {
        localStorage.setItem("custom_bg_dataurl", result);
      } catch (err) {
        // ignore quota errors silently
      }
      setBgUrl(result);
    };
    reader.readAsDataURL(file);
  };

  const onMusicFileChange = (e: React.ChangeEvent<HTMLInputElement>) => {
    const file = e.target.files && e.target.files[0];
    if (!file) return;
    const url = URL.createObjectURL(file);
    setAudioSrc(url);
    // try playing (may be blocked until user gesture)
    setTimeout(() => {
      try { audioRef.current?.play(); } catch {}
    }, 50);
  };

  const onPlayClick = () => {
    try {
      if (audioRef.current) {
        audioRef.current.muted = false;
        audioRef.current.play();
      }
    } catch {}
  };

  // ---------- Helpers for notes persistence ----------
  const getNote = (key: string) => {
    try { return localStorage.getItem("nota_" + key) || ""; } catch { return ""; }
  };
  const setNote = (key: string, value: string) => {
    try { localStorage.setItem("nota_" + key, value); } catch {}
  };

  // Attempt to restore a custom background if previously saved
  useEffect(() => {
    try {
      const saved = localStorage.getItem("custom_bg_dataurl");
      if (saved) setBgUrl(saved);
    } catch {}
  }, []);

  // ---------- Simple in-app tests (self-check) ----------
  type TestResult = { name: string; pass: boolean; message?: string };
  const [testResults, setTestResults] = useState<TestResult[]>([]);

  useEffect(() => {
    const results: TestResult[] = [];

    // Test 1: Background loads (string non-empty)
    results.push({
      name: "Background URL present",
      pass: typeof bgUrl === "string" && bgUrl.length > 0,
      message: bgUrl,
    });

    // Test 2: Header Megumin image path not empty
    results.push({
      name: "Megumin image path",
      pass: !!meguminPath,
      message: meguminPath,
    });

    // Test 3: Audio element exists and has a source
    const audioHasSrc = !!audioRef.current && !!audioRef.current.src;
    results.push({ name: "Audio element + src", pass: audioHasSrc, message: audioRef.current?.src });

    // Test 4: LocalStorage round-trip for notes
    const probeKey = "__probe__";
    const probeVal = "ok" + Math.random().toString(16).slice(2, 6);
    try {
      localStorage.setItem("nota_" + probeKey, probeVal);
      const got = localStorage.getItem("nota_" + probeKey);
      results.push({ name: "LocalStorage notes", pass: got === probeVal });
      localStorage.removeItem("nota_" + probeKey);
    } catch {
      results.push({ name: "LocalStorage notes", pass: false, message: "Exception" });
    }

    // Test 5: Friday block exists
    const fridayBlock = document.getElementById("bloque-viernes");
    results.push({ name: "Friday block present", pass: !!fridayBlock });

    setTestResults(results);
  }, [bgUrl]);

  const testsPassed = testResults.filter((t) => t.pass).length;

  // ---------- UI ----------
  return (
    <div
      className="min-h-screen w-full text-slate-100"
      style={{ backgroundImage: `url(${bgUrl})`, backgroundSize: "cover", backgroundPosition: "center" }}
    >
      {/* Overlay to ensure readability */}
      <div className="min-h-screen backdrop-blur-sm bg-slate-900/40">
        {/* Header */}
        <header className="sticky top-0 z-10 flex items-center gap-3 px-4 py-3 bg-slate-900/60 border-b border-white/10">
          <img
            src={meguminPath}
            alt="Megumin con desayuno"
            className="w-20 h-20 rounded-2xl object-cover ring-2 ring-pink-500/60 shadow-xl"
          />
          <h1 className="text-lg md:text-2xl font-extrabold tracking-tight">QUE SE DESAPAREZCA ESTÁ MRD# XD</h1>
        </header>

        {/* Controls */}
        <main className="max-w-6xl mx-auto p-4 space-y-4">
          <section className="rounded-2xl p-4 bg-white/90 text-slate-900 shadow">
            <h2 className="text-xl font-bold mb-2">Personaliza la página</h2>
            <div className="flex flex-col md:flex-row md:items-center gap-3">
              <label className="inline-flex items-center gap-2">
                <span className="text-sm">Cambiar fondo (Kinich, etc.)</span>
                <input type="file" accept="image/*" onChange={onBgFileChange} className="text-sm" />
              </label>
              <span className="text-xs text-slate-500">Si no subes nada, se usa <b>hq720.jpg</b> del repositorio.</span>
            </div>

            <div className="mt-3 flex flex-col md:flex-row md:items-center gap-3">
              <audio ref={audioRef} controls autoPlay loop preload="auto" playsInline className="w-72">
                <source src={audioSrc} />
              </audio>
              <label className="inline-flex items-center gap-2">
                <span className="text-sm">Subir música</span>
                <input type="file" accept="audio/*" onChange={onMusicFileChange} className="text-sm" />
              </label>
              <button onClick={onPlayClick} className="px-3 py-2 rounded-lg bg-slate-800 text-slate-100 border border-white/20">
                ▶ Reproducir
              </button>
              <span className="text-xs text-slate-500">En algunos móviles el autoplay se bloquea hasta que tocas reproducir.</span>
            </div>
          </section>

          {/* Plan semanal */}
          <section className="grid md:grid-cols-2 xl:grid-cols-3 gap-4">
            <DayCard id="bloque-lun-jue" title="Lunes – Jueves"
              blocks={[
                { label: "Desayuno", desc: "Chocolate con pan + 1 fruta (naranja, papaya, etc.) + 1 vaso de agua.", key: "lun_jue_desayuno" },
                { label: "Media mañana", desc: "Yogur natural con avena o almendras.", key: "lun_jue_media" },
                { label: "Almuerzo", desc: "Arroz integral + pechuga de pollo a la plancha + ensalada (espinaca, zanahoria).", key: "lun_jue_almuerzo" },
                { label: "Merienda", desc: "Batido de frutas sin azúcar añadida.", key: "lun_jue_merienda" },
                { label: "Cena", desc: "Sopa ligera de verduras + pescado a la plancha.", key: "lun_jue_cena" },
              ]}
              getNote={getNote}
              setNote={setNote}
            />

            <DayCard id="bloque-viernes" title="Viernes (fuera todo el día, estómago sensible)"
              blocks={[
                { label: "Desayuno", desc: "Chocolate con pan + banano maduro + agua.", key: "vie_desayuno" },
                { label: "Snack para llevar", desc: "Galletas integrales simples + botella de agua / kumis o yogur natural.", key: "vie_snack" },
                { label: "Almuerzo afuera", desc: "Wrap integral de pollo y vegetales, o arroz blanco + pollo/pescado a la plancha + ensalada suave.", key: "vie_almuerzo" },
                { label: "Merienda tarde", desc: "Fruta portable (manzana, pera) + agua.", key: "vie_merienda" },
                { label: "Cena", desc: "Sopa ligera / arroz blanco con atún y verduras al vapor.", key: "vie_cena" },
              ]}
              getNote={getNote}
              setNote={setNote}
            />

            <DayCard id="bloque-sab-dom" title="Sábado – Domingo"
              blocks={[
                { label: "Desayuno", desc: "Chocolate con pan + papaya.", key: "sab_dom_desayuno" },
                { label: "Media mañana", desc: "Frutos secos (poca cantidad).", key: "sab_dom_media" },
                { label: "Almuerzo", desc: "Lentejas + ensalada + proteína magra.", key: "sab_dom_almuerzo" },
                { label: "Merienda", desc: "Yogur + fruta.", key: "sab_dom_merienda" },
                { label: "Cena", desc: "Sopa + huevo hervido con verduras.", key: "sab_dom_cena" },
              ]}
              getNote={getNote}
              setNote={setNote}
            />
          </section>

          <section className="rounded-2xl p-4 bg-white/90 text-slate-800 shadow">
            <strong>Recordatorios rápidos:</strong> hidrátate (2 L/día), limita fritos/azúcar/lácteos en exceso, incluye omega‑3 (pescado/chía/linaza), protector solar si la espalda se expone.
          </section>
        </main>

        {/* Footer */}
        <footer className="text-xs text-slate-300 bg-black/60 border-t border-white/10 text-center py-3">
          © 2025 ChatGPT & Maintel — página de prueba/portafolio. Este sitio usa contenido subido por el autor con fines no comerciales.
        </footer>

        {/* Tiny test results widget (bottom-right) */}
        <div className="fixed bottom-2 right-2 text-[10px] bg-black/60 text-white rounded px-2 py-1 border border-white/20">
          Tests: {testsPassed}/{testResults.length}
        </div>
      </div>
    </div>
  );
}

// ---------- Subcomponents ----------
function DayCard({
  id,
  title,
  blocks,
  getNote,
  setNote,
}: {
  id: string;
  title: string;
  blocks: { label: string; desc: string; key: string }[];
  getNote: (key: string) => string;
  setNote: (key: string, value: string) => void;
}) {
  return (
    <article id={id} className="rounded-2xl p-4 bg-white/90 text-slate-900 shadow">
      <h3 className="text-lg font-bold mb-2">{title}</h3>
      {blocks.map((b) => (
        <div key={b.key} className="mb-3">
          <div className="font-semibold text-slate-900">{b.label}</div>
          <div className="text-slate-700 mb-2">{b.desc}</div>
          <textarea
            defaultValue={getNote(b.key)}
            onChange={(e) => setNote(b.key, e.target.value)}
            className="w-full min-h-[56px] p-2 rounded-lg border border-slate-300 bg-slate-50 text-slate-900"
            placeholder="Notas…"
          />
        </div>
      ))}
    </article>
  );
}
