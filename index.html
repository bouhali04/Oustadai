export default async function handler(req, res) {
  res.setHeader('Access-Control-Allow-Origin', '*');
  res.setHeader('Access-Control-Allow-Methods', 'POST, OPTIONS');
  res.setHeader('Access-Control-Allow-Headers', 'Content-Type');
  if (req.method === 'OPTIONS') return res.status(200).end();
  if (req.method !== 'POST') return res.status(405).json({ error: 'Method not allowed' });

  const SYSTEM = `Tu es OustadAI, un assistant scolaire pour les élèves marocains du primaire, collège et lycée.
Tu comprends et parles en darija marocain (écriture latine : wash, 3awd, zwin, mochkil, wach fhemti, mazal, chno, bzzaf...) ET en français ET en arabe.
Si l'élève écrit en darija, tu réponds d'abord en darija puis tu expliques en français.
Si l'élève écrit en français, tu réponds en français avec quelques mots de darija.
Tu aides avec : maths, sciences, histoire-géo, français, arabe, physique, chimie, SVT.
Tu donnes des explications simples avec des exemples du quotidien marocain.
Tu es encourageant, patient et positif. Maximum 200 mots par réponse.`;

  try {
    const { messages } = req.body;
    const apiKey = process.env.GEMINI_API_KEY;

    const response = await fetch(
      `https://generativelanguage.googleapis.com/v1beta/models/gemini-1.5-flash:generateContent?key=${apiKey}`,
      {
        method: 'POST',
        headers: { 'Content-Type': 'application/json' },
        body: JSON.stringify({
          system_instruction: { parts: [{ text: SYSTEM }] },
          contents: messages
        })
      }
    );

    const data = await response.json();
    if (data.error) return res.status(400).json({ error: data.error.message });
    const reply = data.candidates?.[0]?.content?.parts?.[0]?.text || '';
    res.status(200).json({ reply });
  } catch (e) {
    res.status(500).json({ error: e.message });
  }
}
