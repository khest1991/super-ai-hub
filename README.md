import { useState } from "react";
import { Button } from "@/components/ui/button";
import { Card, CardContent } from "@/components/ui/card";
import { Input } from "@/components/ui/input";
import { Check, Shield, Zap, Globe, Menu, X, Star, Lock, Rocket, Sparkles } from "lucide-react";

export default function MainLanding() {
  const [lang, setLang] = useState<'ar' | 'en'>('ar');
  const [mobileOpen, setMobileOpen] = useState(false);
  const [email, setEmail] = useState("");
  const [subscribed, setSubscribed] = useState(false);

  const t = {
    ar: {
      brand: 'Super AI Hub',
      title: 'Super AI Hub — منصتك الذكية الشاملة',
      subtitle: 'أنشئ محتوى، صمّم صور، لخّص دروس، وطوّر عملك في مكان واحد.',
      cta: 'ابدأ مجانًا',
      cta2: 'شاهد الأسعار',
      ann: 'جديد: باقة Pro بـ 10$ شهريًا — جرّبها الآن',
      nav: { features: 'المزايا', how: 'كيف يعمل', pricing: 'الأسعار', faq: 'الأسئلة', blog: 'المدونة', signin: 'تسجيل الدخول' },
      featuresTitle: 'ماذا ستحصل؟',
      f1: { h: '✍️ كتابة ذكية', p: 'مقالات وبوستات وإعلانات خلال ثوانٍ.' },
      f2: { h: '🎨 صور بالذكاء', p: 'صوّر أفكارك بصور جاهزة للنشر.' },
      f3: { h: '🎓 مساعد دراسي', p: 'تلخيص واختبارات وشرح مبسّط.' },
      f4: { h: '📊 أدوات أعمال', p: 'خطط مشاريع وتحليل منافسين ورسائل احترافية.' },
      f5: { h: '⚡ أداء سريع', p: 'بنية سريعة تدعم آلاف الطلبات.' },
      f6: { h: '🔒 خصوصية وأمان', p: 'تخزين آمن وشفافية في الاستخدام.' },
      howTitle: 'كيف يعمل؟',
      step1: 'سجِّل حسابًا وادخل لوحة التحكم',
      step2: 'اختر أداتك: كتابة / صور / تعليم / أعمال',
      step3: 'ادفع باشتراك أو عبر رصيد حسب استخدامك',
      useCasesTitle: 'حالات الاستخدام',
      u1: { h: 'صنّاع المحتوى', p: 'مقالات، عناوين جذابة، صور منشورات.' },
      u2: { h: 'طلاب ومعلمون', p: 'تلخيص دروس، أسئلة اختبار، تبسيط مفاهيم.' },
      u3: { h: 'مشاريع وشركات ناشئة', p: 'تحليل منافسين، خطط تسويق ورسائل مهنية.' },
      integrations: 'نحن نتكامل مع أفضل الأدوات',
      plansTitle: 'الأسعار',
      free: 'مجاني', pro: 'احترافي', business: 'شركات',
      selectPlan: 'اختر الباقة',
      testimonials: 'ماذا يقول مستخدمونا؟',
      securityTitle: 'الأمان والخصوصية أولاً',
      s1: 'اتصال مشفّر HTTPS دائمًا',
      s2: 'سياسات صارمة لحماية البيانات',
      s3: 'دفع آمن عبر Stripe',
      newsletterTitle: 'اشترك في النشرة',
      newsletterDesc: 'نرسل أفضل التحديثات والنصائح مرة أسبوعيًا.',
      emailPlaceholder: 'أدخل بريدك الإلكتروني',
      subscribe: 'اشترك',
      subscribed: 'تم الاشتراك بنجاح ✔',
      faqTitle: 'الأسئلة الشائعة',
      q1: 'هل يمكن الإلغاء في أي وقت؟', a1: 'نعم، يمكنك الإلغاء من صفحة الحساب دون رسوم.',
      q2: 'هل المحتوى يدعم العربية؟', a2: 'نعم، يدعم العربية والإنجليزية بشكل كامل.',
      q3: 'هل يوجد تجربة مجانية؟', a3: 'نعم، باقة مجانية بـ 10 عمليات شهريًا.',
      footer: '© جميع الحقوق محفوظة — Super AI Hub',
      langSwitch: 'English',
      pricing: 'الانتقال للتسعير',
      dashboard: 'اذهب للتطبيق',
      admin: 'لوحة الإدارة'
    },
    en: {
      brand: 'Super AI Hub',
      title: 'Super AI Hub — Your all‑in‑one AI platform',
      subtitle: 'Write content, generate images, study faster, and grow your business in one place.',
      cta: 'Start Free',
      cta2: 'See Pricing',
      ann: 'New: Pro plan $10/mo — try it now',
      nav: { features: 'Features', how: 'How it works', pricing: 'Pricing', faq: 'FAQ', blog: 'Blog', signin: 'Sign in' },
      featuresTitle: 'What you get',
      f1: { h: '✍️ Smart Writing', p: 'Blogs, posts and ads in seconds.' },
      f2: { h: '🎨 AI Images', p: 'Turn ideas into ready‑to‑share visuals.' },
      f3: { h: '🎓 Study Assistant', p: 'Summaries, quizzes and clear explanations.' },
      f4: { h: '📊 Business Tools', p: 'Plans, competitor insights, pro emails.' },
      f5: { h: '⚡ Fast Performance', p: 'Scales to thousands of requests.' },
      f6: { h: '🔒 Privacy & Security', p: 'Secure storage and transparent usage.' },
      howTitle: 'How it works',
      step1: 'Sign up and access the dashboard',
      step2: 'Pick a tool: Content / Images / Study / Business',
      step3: 'Pay by subscription or pay‑as‑you‑go credits',
      useCasesTitle: 'Use cases',
      u1: { h: 'Creators', p: 'Articles, catchy titles, social images.' },
      u2: { h: 'Students & Teachers', p: 'Summaries, quizzes, concept simplification.' },
      u3: { h: 'Startups & Teams', p: 'Competitor research, marketing plans, outreach.' },
      integrations: 'We integrate with the best tools',
      plansTitle: 'Pricing',
      free: 'Free', pro: 'Pro', business: 'Business',
      selectPlan: 'Select plan',
      testimonials: 'What users say',
      securityTitle: 'Security & privacy first',
      s1: 'Always-on HTTPS encryption',
      s2: 'Strict data-protection policies',
      s3: 'Secure payments via Stripe',
      newsletterTitle: 'Join the newsletter',
      newsletterDesc: 'Weekly tips and product updates — no spam.',
      emailPlaceholder: 'Enter your email',
      subscribe: 'Subscribe',
      subscribed: 'Subscribed ✔',
      faqTitle: 'FAQ',
      q1: 'Can I cancel anytime?', a1: 'Yes, cancel from your profile with no fees.',
      q2: 'Does it support Arabic?', a2: 'Yes, full Arabic & English support.',
      q3: 'Is there a free trial?', a3: 'Yes — Free plan includes 10 ops/month.',
      footer: '© All rights reserved — Super AI Hub',
      langSwitch: 'العربية',
      pricing: 'Go to Pricing',
      dashboard: 'Go to App',
      admin: 'Admin'
    }
  }[lang];

  const scrollTo = (id: string) => {
    const el = document.getElementById(id);
    if (el) el.scrollIntoView({ behavior: 'smooth', block: 'start' });
    setMobileOpen(false);
  };

  const onSubscribe = (e: React.FormEvent) => {
    e.preventDefault();
    if (!email || !/^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(email)) return alert(lang==='ar'?'يرجى إدخال بريد صحيح':'Please enter a valid email');
    setSubscribed(true);
    setEmail("");
  };

  const dir = lang==='ar'?'direction-rtl':'direction-ltr';

  return (
    <div className={`min-h-screen ${dir} bg-gradient-to-b from-white to-gray-50`}>
      {/* Announcement */}
      <div className="w-full text-center text-sm py-2 px-3 bg-indigo-600 text-white">{t.ann}</div>

      {/* Header */}
      <header className="sticky top-0 z-40 backdrop-blur bg-white/70 border-b">
        <div className="max-w-7xl mx-auto px-4 py-3 flex items-center justify-between">
          <div className="flex items-center gap-2">
            <div className="w-8 h-8 rounded-xl bg-indigo-600" />
            <span className="font-bold text-lg text-indigo-700">{t.brand}</span>
          </div>
          <nav className="hidden md:flex items-center gap-5 text-sm text-gray-700">
            <button onClick={()=>scrollTo('features')} className="hover:text-indigo-600">{t.nav.features}</button>
            <button onClick={()=>scrollTo('how')} className="hover:text-indigo-600">{t.nav.how}</button>
            <a href="/pricing" className="hover:text-indigo-600">{t.nav.pricing}</a>
            <button onClick={()=>scrollTo('faq')} className="hover:text-indigo-600">{t.nav.faq}</button>
            <a href="#" className="hover:text-indigo-600">{t.nav.blog}</a>
          </nav>
          <div className="hidden md:flex items-center gap-2">
            <Button variant="ghost" onClick={()=>setLang(lang==='ar'?'en':'ar')}>{t.langSwitch}</Button>
            <a href="/admin" className="hidden lg:block"><Button variant="ghost">{t.admin}</Button></a>
            <a href="/pricing"><Button>{t.cta}</Button></a>
          </div>
          {/* Mobile */}
          <div className="md:hidden flex items-center gap-2">
            <Button variant="ghost" onClick={()=>setLang(lang==='ar'?'en':'ar')}>{t.langSwitch}</Button>
            <Button variant="outline" size="icon" onClick={()=>setMobileOpen(!mobileOpen)} aria-label="Menu">
              {mobileOpen? <X size={18}/> : <Menu size={18}/>}
            </Button>
          </div>
        </div>
        {mobileOpen && (
          <div className="md:hidden px-4 pb-4 space-y-2 border-t bg-white">
            <button onClick={()=>scrollTo('features')} className="block w-full text-left py-2">{t.nav.features}</button>
            <button onClick={()=>scrollTo('how')} className="block w-full text-left py-2">{t.nav.how}</button>
            <a href="/pricing" className="block w-full py-2">{t.nav.pricing}</a>
            <button onClick={()=>scrollTo('faq')} className="block w-full text-left py-2">{t.nav.faq}</button>
            <a href="#" className="block w-full py-2">{t.nav.blog}</a>
            <a href="/admin" className="block w-full py-2">{t.admin}</a>
            <a href="/pricing" className="block w-full py-2"><Button className="w-full">{t.cta}</Button></a>
          </div>
        )}
      </header>

      {/* Hero */}
      <section className="px-6 py-16 text-center max-w-6xl mx-auto">
        <h1 className="text-4xl md:text-6xl font-extrabold leading-tight">{t.title}</h1>
        <p className="mt-4 text-gray-600 text-lg md:text-xl">{t.subtitle}</p>
        <div className="mt-8 flex items-center justify-center gap-3">
          <a href="/pricing"><Button size="lg">{t.cta}</Button></a>
          <a href="#plans"><Button variant="outline" size="lg">{t.cta2}</Button></a>
        </div>
        {/* Trust badges */}
        <div className="mt-10 grid grid-cols-2 md:grid-cols-4 gap-3 text-sm text-gray-500">
          <div className="flex items-center justify-center gap-2 p-3 rounded-xl bg-white border"><Shield size={16}/> <span>Stripe</span></div>
          <div className="flex items-center justify-center gap-2 p-3 rounded-xl bg-white border"><Rocket size={16}/> <span>Next.js</span></div>
          <div className="flex items-center justify-center gap-2 p-3 rounded-xl bg-white border"><Sparkles size={16}/> <span>OpenAI</span></div>
          <div className="flex items-center justify-center gap-2 p-3 rounded-xl bg-white border"><Globe size={16}/> <span>PostgreSQL</span></div>
        </div>
      </section>

      {/* Features */}
      <section id="features" className="px-6 py-10 max-w-7xl mx-auto">
        <h2 className="text-2xl md:text-3xl font-bold mb-6 text-center">{t.featuresTitle}</h2>
        <div className="grid sm:grid-cols-2 lg:grid-cols-3 gap-4">
          {[t.f1,t.f2,t.f3,t.f4,t.f5,t.f6].map((f, i) => (
            <Card key={i} className="rounded-2xl shadow-sm border">
              <CardContent className="p-6">
                <h3 className="font-semibold text-lg mb-2">{f.h}</h3>
                <p className="text-gray-600 text-sm">{f.p}</p>
                <div className="mt-4 flex items-center gap-2 text-green-600 text-sm"><Check size={16}/> {lang==='ar'?'سهل الاستخدام':'Easy to use'}</div>
              </CardContent>
            </Card>
          ))}
        </div>
      </section>

      {/* How it works */}
      <section id="how" className="px-6 py-10 max-w-6xl mx-auto">
        <h2 className="text-2xl md:text-3xl font-bold mb-6 text-center">{t.howTitle}</h2>
        <div className="grid md:grid-cols-3 gap-4 text-center">
          {[t.step1,t.step2,t.step3].map((s, i) => (
            <div key={i} className="p-6 bg-white rounded-2xl shadow-sm border">
              <p className="text-gray-700 font-medium">{s}</p>
            </div>
          ))}
        </div>
      </section>

      {/* Use cases */}
      <section className="px-6 py-10 max-w-6xl mx-auto">
        <h2 className="text-2xl md:text-3xl font-bold mb-6 text-center">{t.useCasesTitle}</h2>
        <div className="grid md:grid-cols-3 gap-4">
          {[t.u1,t.u2,t.u3].map((u, i)=> (
            <Card key={i} className="rounded-2xl border">
              <CardContent className="p-6">
                <h3 className="font-semibold text-lg mb-2">{u.h}</h3>
                <p className="text-gray-600 text-sm">{u.p}</p>
              </CardContent>
            </Card>
          ))}
        </div>
      </section>

      {/* Integrations banner */}
      <section className="px-6 py-10 max-w-6xl mx-auto text-center">
        <p className="text-gray-600">{t.integrations}</p>
        <div className="mt-4 flex flex-wrap items-center justify-center gap-3">
          <span className="px-3 py-2 rounded-lg bg-white border">OpenAI</span>
          <span className="px-3 py-2 rounded-lg bg-white border">Stripe</span>
          <span className="px-3 py-2 rounded-lg bg-white border">Next.js</span>
          <span className="px-3 py-2 rounded-lg bg-white border">PostgreSQL</span>
        </div>
      </section>

      {/* Plans */}
      <section id="plans" className="px-6 py-12 max-w-7xl mx-auto">
        <h2 className="text-2xl md:text-3xl font-bold mb-6 text-center">{t.plansTitle}</h2>
        <div className="grid md:grid-cols-3 gap-4">
          {[{n:t.free,p:'$0/mo',k:['10 ops','Basic support']},{n:t.pro,p:'$10/mo',k:['500 ops','All tools','Export PDF/Word']},{n:t.business,p:'$30/mo',k:['Unlimited + 5 users','Priority support']}].map((pl, i)=> (
            <Card key={i} className={`rounded-2xl ${i===1?'border-2 border-indigo-500 bg-indigo-50':''}`}>
              <CardContent className="p-6">
                <h3 className="font-bold text-xl mb-2">{pl.n}</h3>
                <p className="text-gray-700 mb-4">{pl.p}</p>
                <ul className="text-sm text-gray-700 space-y-1 mb-4">
                  {pl.k.map((k,idx)=>(<li key={idx} className="flex items-center gap-2"><Check size={16} className="text-green-600"/> {k}</li>))}
                </ul>
                <a href="/pricing"><Button className="w-full">{t.selectPlan}</Button></a>
              </CardContent>
            </Card>
          ))}
        </div>
      </section>

      {/* Testimonials */}
      <section className="px-6 py-10 max-w-6xl mx-auto">
        <h2 className="text-2xl md:text-3xl font-bold mb-6 text-center">{t.testimonials}</h2>
        <div className="grid md:grid-cols-3 gap-4">
          {[1,2,3].map((i)=> (
            <Card key={i} className="rounded-2xl border">
              <CardContent className="p-6">
                <div className="flex items-center gap-1 text-yellow-500 mb-2"><Star size={16}/><Star size={16}/><Star size={16}/><Star size={16}/><Star size={16}/></div>
                <p className="text-gray-700 text-sm">{lang==='ar'? 'وفّر عليّ ساعات كتابة يوميًا—أنصح به.':'Saved me hours of writing every day — highly recommended.'}</p>
                <div className="mt-3 text-sm text-gray-500">{lang==='ar'? 'مريم – صانعة محتوى':'Maryam – Content Creator'}</div>
              </CardContent>
            </Card>
          ))}
        </div>
      </section>

      {/* Security */}
      <section className="px-6 py-10 max-w-6xl mx-auto">
        <h2 className="text-2xl md:text-3xl font-bold mb-6 text-center">{t.securityTitle}</h2>
        <div className="grid md:grid-cols-3 gap-4">
          {[t.s1,t.s2,t.s3].map((s, i)=> (
            <div key={i} className="flex items-center gap-3 bg-white border rounded-2xl p-4">
              <Lock size={18} className="text-indigo-600"/> <span className="text-gray-700 text-sm">{s}</span>
            </div>
          ))}
        </div>
      </section>

      {/* Newsletter */}
      <section className="px-6 py-12 max-w-3xl mx-auto text-center">
        <h3 className="text-2xl font-bold mb-2">{t.newsletterTitle}</h3>
        <p className="text-gray-600 mb-4">{t.newsletterDesc}</p>
        {subscribed ? (
          <div className="text-green-600 font-medium">{t.subscribed}</div>
        ) : (
          <form onSubmit={onSubscribe} className="flex flex-col sm:flex-row items-center gap-2 justify-center">
            <Input value={email} onChange={(e)=>setEmail(e.target.value)} placeholder={t.emailPlaceholder} className="w-full sm:w-80"/>
            <Button type="submit">{t.subscribe}</Button>
          </form>
        )}
      </section>

      {/* FAQ */}
      <section id="faq" className="px-6 py-10 max-w-4xl mx-auto">
        <h2 className="text-2xl md:text-3xl font-bold mb-6 text-center">{t.faqTitle}</h2>
        <div className="space-y-3">
          <details className="bg-white rounded-2xl p-4 border"><summary className="cursor-pointer font-medium">{t.q1}</summary><p className="mt-2 text-gray-600 text-sm">{t.a1}</p></details>
          <details className="bg-white rounded-2xl p-4 border"><summary className="cursor-pointer font-medium">{t.q2}</summary><p className="mt-2 text-gray-600 text-sm">{t.a2}</p></details>
          <details className="bg-white rounded-2xl p-4 border"><summary className="cursor-pointer font-medium">{t.q3}</summary><p className="mt-2 text-gray-600 text-sm">{t.a3}</p></details>
        </div>
      </section>

      {/* Footer */}
      <footer className="px-6 py-10 text-center text-sm text-gray-500">
        <div className="mb-3 flex items-center justify-center gap-3 text-gray-600">
          <a className="underline" href="/pricing">{t.pricing}</a>
          <a className="underline" href="/admin">{t.admin}</a>
          <a className="underline" href="/">{t.dashboard}</a>
        </div>
        {t.footer}
      </footer>

      {/* JSON-LD (SEO) */}
      <script type="application/ld+json" dangerouslySetInnerHTML={{ __html: JSON.stringify({
        "@context": "https://schema.org",
        "@type": "SoftwareApplication",
        name: t.brand,
        applicationCategory: "BusinessApplication",
        offers: { "@type": "Offer", price: "10", priceCurrency: "USD" }
      }) }} />
    </div>
  );
}
