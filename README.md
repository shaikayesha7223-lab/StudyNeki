# StudyNeko
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>StudyNeko · Small Steps, Big Dreams 🌸</title>
<meta name="theme-color" content="#f7b8cf" />
<link rel="manifest" href="data:application/manifest+json,%7B%22name%22%3A%22StudyNeko%22%2C%22short_name%22%3A%22StudyNeko%22%2C%22start_url%22%3A%22.%22%2C%22display%22%3A%22standalone%22%2C%22background_color%22%3A%22%23fdf8f5%22%2C%22theme_color%22%3A%22%23f7b8cf%22%2C%22icons%22%3A%5B%7B%22src%22%3A%22data%3Aimage%2Fsvg%2Bxml%2C%253Csvg%2520xmlns%253D%2527http%253A%2F%2Fwww.w3.org%2F2000%2Fsvg%2527%2520viewBox%253D%25270%25200%2520512%2520512%2527%253E%253Ccircle%2520cx%253D%2527256%2527%2520cy%253D%2527256%2527%2520r%253D%2527256%2527%2520fill%253D%2527%2523f7b8cf%2527%2F%253E%253Ctext%2520x%253D%2527256%2527%2520y%253D%2527350%2527%2520font-size%253D%2527320%2527%2520text-anchor%253D%2527middle%2527%253E%25F0%259F%258C%25B8%253C%2Ftext%253E%253C%2Fsvg%253E%22%2C%22sizes%22%3A%22512x512%22%2C%22type%22%3A%22image%2Fsvg%2Bxml%22%7D%5D%7D" />
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Quicksand:wght@400;500;600;700&display=swap" rel="stylesheet">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
<script src="https://unpkg.com/react@18/umd/react.production.min.js"></script>
<script src="https://unpkg.com/react-dom@18/umd/react-dom.production.min.js"></script>
<script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
<style>
  *{margin:0;padding:0;box-sizing:border-box;font-family:'Quicksand',sans-serif}
  :root{--pink:#f9d9e6;--pink-s:#f7b8cf;--lav:#e5d9f2;--lav-s:#d4c0e8;--bg:#fdf8f5;--card:#fff;--text:#3a2e2a;--muted:#7a6a64;--border:#f0e4de;--shadow:0 10px 25px -8px rgba(0,0,0,.08)}
  body.dark{--bg:#231f1e;--card:#332d2a;--text:#f0e7e2;--muted:#c7bab3;--border:#4a3f3a;--pink:#4a3a3f;--pink-s:#6b4e5a;--lav:#3d3646;--lav-s:#5a4a66}
  body{background:var(--bg);color:var(--text);transition:.3s;padding:16px;padding-bottom:80px}
  .container{max-width:1300px;margin:0 auto}
  header{display:flex;flex-wrap:wrap;gap:12px;justify-content:space-between;align-items:center;margin-bottom:16px}
  .logo{font-size:1.8rem;font-weight:700;background:linear-gradient(135deg,#f7b8cf,#b8a2e0);-webkit-background-clip:text;background-clip:text;-webkit-text-fill-color:transparent}
  .tag{font-size:.75rem;color:var(--muted)}
  .btn{background:var(--card);border:1px solid var(--border);border-radius:50px;padding:9px 14px;font-weight:600;font-size:.85rem;color:var(--text);cursor:pointer;transition:.2s;display:inline-flex;align-items:center;gap:6px;box-shadow:var(--shadow)}
  .btn:hover{transform:translateY(-2px)}
  .btn.primary{background:var(--pink-s);color:#2e1e26;border:none}
  .btn.lav{background:var(--lav);border:none}
  body.dark .btn.primary{background:#6b4e5a;color:#f0e7e2}
  .btn.sm{padding:6px 12px;font-size:.78rem}
  .btn.danger{background:#f5c6c6;color:#7a3a3a;border:none}
  body.dark .btn.danger{background:#5a3a3a;color:#f0c0c0}
  nav{overflow-x:auto;white-space:nowrap;margin-bottom:16px;padding-bottom:4px}
  nav::-webkit-scrollbar{display:none}
  .nav{display:flex;gap:8px}
  .nav button{flex-shrink:0}
  .nav button.active{background:var(--pink-s);color:#2e1e26;border:none}
  body.dark .nav button.active{background:#6b4e5a;color:#f0e7e2}
  .card{background:var(--card);border-radius:24px;padding:20px;box-shadow:var(--shadow);border:1px solid var(--border);margin-bottom:16px}
  .card h3{font-size:1.05rem;margin-bottom:10px;display:flex;align-items:center;gap:8px}
  .grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(260px,1fr));gap:16px}
  .flex{display:flex;align-items:center;gap:10px;flex-wrap:wrap}
  .between{display:flex;justify-content:space-between;align-items:center;flex-wrap:wrap;gap:10px}
  .big{font-size:1.8rem;font-weight:700;color:#b87b9a}
  body.dark .big{color:#e7b7c9}
  .bar{background:var(--border);border-radius:100px;height:12px;overflow:hidden;margin:6px 0}
  .fill{height:100%;background:linear-gradient(90deg,#f7b8cf,#d4c0e8);border-radius:100px;transition:width .4s}
  .task{display:flex;align-items:center;gap:10px;padding:10px 0;border-bottom:1px solid var(--border)}
  .task:last-child{border:none}
  .chk{width:22px;height:22px;border-radius:50%;border:2px solid var(--pink-s);background:transparent;cursor:pointer;display:flex;align-items:center;justify-content:center;color:transparent;font-size:.7rem}
  .chk.done{background:var(--pink-s);color:#fff}
  .done-txt{text-decoration:line-through;color:var(--muted)}
  input,select,textarea{background:var(--bg);border:1px solid var(--border);border-radius:14px;padding:10px 14px;font-size:.88rem;font-family:inherit;color:var(--text);width:100%}
  input:focus,select:focus,textarea:focus{outline:none;border-color:var(--pink-s)}
  .badge{background:var(--lav);color:#4a3a3f;padding:3px 10px;border-radius:50px;font-size:.72rem;font-weight:600}
  body.dark .badge{background:var(--lav-s);color:#fff}
  .unit{background:var(--bg);border-radius:18px;padding:16px;margin-bottom:12px;border:1px solid var(--border)}
  .topic{display:flex;align-items:center;gap:8px;padding:4px 0;font-size:.88rem}
  .flash{background:var(--lav);border-radius:24px;padding:30px;text-align:center;cursor:pointer;min-height:170px;display:flex;flex-direction:column;align-items:center;justify-content:center;user-select:none;transition:.2s}
  .flash:hover{transform:scale(1.01)}
  .flash .jp{font-size:2.8rem;font-weight:700;color:#4a2e3a}
  .flash .mn{font-size:1.1rem;margin-top:8px;color:#5a4a52}
  .slot{display:flex;gap:10px;align-items:center;padding:8px 0;border-bottom:1px solid var(--border);flex-wrap:wrap}
  .timer{font-size:3rem;font-weight:700;text-align:center;color:#b87b9a;font-variant-numeric:tabular-nums}
  body.dark .timer{color:#e7b7c9}
  .cal{display:grid;grid-template-columns:repeat(7,1fr);gap:4px;margin-top:12px}
  .day{aspect-ratio:1;display:flex;align-items:center;justify-content:center;border-radius:12px;font-size:.85rem;background:var(--bg);border:1px solid var(--border);cursor:pointer;font-weight:500;position:relative}
  .day:hover{background:var(--pink)}
  .day.has{background:var(--pink-s);color:#2e1e26;font-weight:700}
  .day.today{outline:2px solid var(--lav-s)}
  .day.off{opacity:.3}
  .chart{display:flex;align-items:flex-end;gap:8px;height:120px;padding-top:10px}
  .col{flex:1;display:flex;flex-direction:column;align-items:center;gap:6px;height:100%;justify-content:flex-end}
  .bar-v{width:100%;max-width:36px;background:linear-gradient(180deg,#f7b8cf,#d4c0e8);border-radius:8px 8px 4px 4px;transition:height .4s;min-height:4px}
  .lbl{font-size:.7rem;color:var(--muted);font-weight:600}
  .toast{position:fixed;bottom:30px;left:50%;transform:translateX(-50%);background:#3a2e2a;color:#fff;padding:12px 24px;border-radius:50px;font-weight:600;font-size:.9rem;z-index:2000;box-shadow:0 10px 30px rgba(0,0,0,.2);animation:fadeIn .3s}
  .searchbar{display:flex;gap:8px;margin-bottom:16px}
  .searchbar input{flex:1;padding:12px 18px;border-radius:50px}
  .search-results{max-height:400px;overflow-y:auto}
  .search-item{padding:10px;border-bottom:1px solid var(--border);cursor:pointer;border-radius:8px}
  .search-item:hover{background:var(--pink)}
  .search-type{font-size:.7rem;color:var(--muted);font-weight:600}
  .quiz-q{font-size:1.1rem;font-weight:600;margin-bottom:12px;text-align:center}
  .quiz-opt{display:block;width:100%;text-align:left;padding:12px 16px;border:1px solid var(--border);border-radius:14px;margin-bottom:8px;background:var(--bg);cursor:pointer;font-size:.9rem;font-weight:500;color:var(--text);transition:.2s}
  .quiz-opt:hover{background:var(--pink)}
  .quiz-opt.correct{background:#c8e6c9;border-color:#81c784;color:#2e5d32}
  .quiz-opt.wrong{background:#ffcdd2;border-color:#e57373;color:#7a3a3a}
  body.dark .quiz-opt.correct{background:#3a5a3f;color:#c8e6c9}
  body.dark .quiz-opt.wrong{background:#5a3a3a;color:#ffcdd2}
  .q-row{display:flex;align-items:center;gap:8px;padding:6px 0;font-size:.85rem;border-bottom:1px dashed var(--border)}
  .q-mark{font-weight:700;color:#b87b9a;min-width:36px}
  .confetti{position:fixed;top:0;left:0;width:100%;height:100%;pointer-events:none;z-index:9999;overflow:hidden}
  .confetti span{position:absolute;width:10px;height:10px;animation:drop 2s linear forwards}
  @keyframes drop{to{transform:translateY(100vh) rotate(720deg);opacity:0}}
  @keyframes fadeIn{from{opacity:0;transform:translateY(8px)}to{opacity:1;transform:translateY(0)}}
  @media(max-width:600px){.logo{font-size:1.4rem}.timer{font-size:2.2rem}.flash .jp{font-size:2rem}.big{font-size:1.5rem}}
</style>
</head>
<body>
<div class="container" id="root"></div>
<div id="toast"></div>
<script type="text/babel" data-presets="react">
const {useState,useEffect,useRef} = React;
const KEY='studyneko_v2';
const uid=p=>p+'-'+Date.now().toString(36)+Math.random().toString(36).slice(2,5);
const todayStr=()=>{const d=new Date();return d.getFullYear()+'-'+String(d.getMonth()+1).padStart(2,'0')+'-'+String(d.getDate()).padStart(2,'0')};
const fmt=s=>new Date(s+'T00:00:00').toLocaleDateString('en-US',{month:'short',day:'numeric',year:'numeric'});
const days=s=>{const t=new Date(s+'T00:00:00'),n=new Date();n.setHours(0,0,0,0);return Math.ceil((t-n)/86400000)};
const greeting=()=>{const h=new Date().getHours();if(h<12)return'Good morning ☀️';if(h<17)return'Good afternoon 🌤️';return'Good evening 🌙'};

const HIRA=[['あ','a'],['い','i'],['う','u'],['え','e'],['お','o'],['か','ka'],['き','ki'],['く','ku'],['け','ke'],['こ','ko'],['さ','sa'],['し','shi'],['す','su'],['せ','se'],['そ','so'],['た','ta'],['ち','chi'],['つ','tsu'],['て','te'],['と','to'],['な','na'],['に','ni'],['ぬ','nu'],['ね','ne'],['の','no'],['は','ha'],['ひ','hi'],['ふ','fu'],['へ','he'],['ほ','ho'],['ま','ma'],['み','mi'],['む','mu'],['め','me'],['も','mo']];
const KATA=[['ア','a'],['イ','i'],['ウ','u'],['エ','e'],['オ','o'],['カ','ka'],['キ','ki'],['ク','ku'],['ケ','ke'],['コ','ko'],['サ','sa'],['シ','shi'],['ス','su'],['セ','se'],['ソ','so'],['タ','ta'],['チ','chi'],['ツ','tsu'],['テ','te'],['ト','to'],['ナ','na'],['ニ','ni'],['ヌ','nu'],['ネ','ne'],['ノ','no']];

function defaults(){
  const subs=[['IRL','Information Retrieval & Learning','2026-11-10'],['GAN','Generative Adversarial Networks','2026-11-12'],['MAS','Multi-Agent Systems','2026-11-16'],['IQTA','Image Quality & Texture Analysis','2026-11-18'],['EDA','Exploratory Data Analysis','2026-11-20'],['GB','Gradient Boosting','2026-11-23']];
  const subjects=subs.map(([code,name,exam])=>({id:code,code,name,examDate:exam,units:Array.from({length:5},(_,i)=>({id:code+'U'+i,name:'Unit '+(i+1),topics:[{id:uid(),text:'Core concepts',done:false},{id:uid(),text:'Important derivations',done:false}],subtopics:'Key points, definitions, formulas',questions:[{id:uid(),mark:2,text:'Define the main concept.'},{id:uid(),mark:5,text:'Explain with example.'},{id:uid(),mark:8,text:'Compare approaches.'},{id:uid(),mark:10,text:'Design a solution.'}],papers:false,notes:'',revised:false}))}));
  const cats=['Vocabulary','Hiragana','Katakana','Kanji','Grammar','Reading','Listening','Speaking'];
  return {theme:'light',subjects,
    jlpt:{examDate:'2026-12-06',cats:Object.fromEntries(cats.map(c=>[c,{progress:0,quizzes:[]}])),
      flashcards:[{jp:'こんにちは',mn:'Hello'},{jp:'ありがとう',mn:'Thank you'},{jp:'さようなら',mn:'Goodbye'},{jp:'ねこ',mn:'Cat'},{jp:'いぬ',mn:'Dog'},{jp:'ほん',mn:'Book'},{jp:'みず',mn:'Water'},{jp:'ごはん',mn:'Rice/Meal'}],
      mistakes:[],streak:0,last:null},
    tasks:[{id:uid(),text:'Review IRL Unit 1',done:false,priority:'high',due:todayStr(),category:'Semester'},{id:uid(),text:'Hiragana quiz',done:false,priority:'medium',due:todayStr(),category:'JLPT'},{id:uid(),text:'Solve GAN paper',done:true,priority:'high',due:todayStr(),category:'Semester'},{id:uid(),text:'Vocabulary flashcards',done:false,priority:'low',due:todayStr(),category:'JLPT'}],
    timetable:[{id:uid(),time:'10:00',subject:'IRL',type:'Study'},{id:uid(),time:'11:30',subject:'Break',type:'Break'},{id:uid(),time:'12:00',subject:'GAN',type:'Study'},{id:uid(),time:'13:30',subject:'Lunch',type:'Meal'},{id:uid(),time:'14:30',subject:'Japanese Vocabulary',type:'JLPT'},{id:uid(),time:'15:30',subject:'MAS',type:'Study'},{id:uid(),time:'17:00',subject:'Break',type:'Break'},{id:uid(),time:'17:30',subject:'IQTA',type:'Study'},{id:uid(),time:'19:00',subject:'Dinner',type:'Meal'},{id:uid(),time:'20:00',subject:'EDA',type:'Study'},{id:uid(),time:'21:30',subject:'Japanese Grammar',type:'JLPT'},{id:uid(),time:'22:30',subject:'Revision',type:'Revision'},{id:uid(),time:'23:00',subject:'GB',type:'Study'}],
    events:[{id:uid(),date:'2026-11-10',title:'IRL Exam',type:'exam'},{id:uid(),date:'2026-11-12',title:'GAN Exam',type:'exam'},{id:uid(),date:'2026-12-06',title:'JLPT N5',type:'exam'}],
    notes:[{id:uid(),title:'IRL key formulas',content:'TF-IDF, cosine similarity...',category:'Semester'},{id:uid(),title:'Japanese particles',content:'は (wa) topic, が (ga) subject...',category:'JLPT'}],
    hours:{mon:2,tue:3,wed:2.5,thu:4,fri:3,sat:1.5,sun:2},
    quotes:['Small steps every day lead to big dreams. 🌸','Believe you can and you\'re halfway there.','The secret of getting ahead is getting started.','Study hard, dream big, stay kind. ✨']};
}
const load=()=>{try{const s=localStorage.getItem(KEY);if(s)return merge(defaults(),JSON.parse(s))}catch(e){}return defaults()};
function merge(b,o){if(Array.isArray(b))return o??b;if(typeof b==='object'&&b&&typeof o==='object'&&o){const r={...b};for(const k in o)r[k]=k in b?merge(b[k],o[k]):o[k];return r}return o??b}

function App(){
  const [data,setData]=useState(load);
  const [page,setPage]=useState('dashboard');
  const [subj,setSubj]=useState(null);
  const [toast,setToast]=useState('');
  const [todoF,setTodoF]=useState('all');
  const [flashI,setFlashI]=useState(0), [flip,setFlip]=useState(false);
  const [pomoSec,setPomoSec]=useState(1500), [pomoOn,setPomoOn]=useState(false);
  const [pomoTask,setPomoTask]=useState('');
  const [cal,setCal]=useState(new Date());
  const [search,setSearch]=useState('');
  const [quiz,setQuiz]=useState(null); // {chars, idx, score, selected, opts}
  const [confetti,setConfetti]=useState(false);

  useEffect(()=>{localStorage.setItem(KEY,JSON.stringify(data))},[data]);
  useEffect(()=>{document.body.classList.toggle('dark',data.theme==='dark')},[data.theme]);
  useEffect(()=>{if(!pomoOn)return;const i=setInterval(()=>{setPomoSec(s=>{if(s<=1){setPomoOn(false);logStudy(25);return 1500}return s-1})},1000);return()=>clearInterval(i)},[pomoOn]);

  const show=m=>{setToast(m);setTimeout(()=>setToast(''),2200)};
  const upd=f=>setData(d=>{const n=JSON.parse(JSON.stringify(d));f(n);return n});
  const logStudy=mins=>{
    const day=['sun','mon','tue','wed','thu','fri','sat'][new Date().getDay()];
    upd(n=>{n.hours[day]=Math.round(((n.hours[day]||0)+mins/60)*10)/10});
  };
  const fireConfetti=()=>{setConfetti(true);setTimeout(()=>setConfetti(false),2200)};

  // Confetti
  const Confetti=()=>{
    if(!confetti)return null;
    const colors=['#f7b8cf','#d4c0e8','#f9d9e6','#e5d9f2','#ffd1dc','#c8b6e2'];
    return <div className="confetti">{Array.from({length:40}).map((_,i)=><span key={i} style={{left:Math.random()*100+'%',background:colors[i%colors.length],animationDelay:Math.random()*0.5+'s'}}/>)}</div>;
  };

  // ================== DASHBOARD ==================
  const Dashboard=()=>{
    const done=data.tasks.filter(t=>t.done).length, tot=data.tasks.length, pct=tot?Math.round(done/tot*100):0;
    const upcoming=data.subjects.filter(s=>days(s.examDate)>=0).sort((a,b)=>new Date(a.examDate)-new Date(b.examDate));
    const next=upcoming[0];
    const quote=data.quotes[new Date().getDate()%data.quotes.length];
    const ds=['mon','tue','wed','thu','fri','sat','sun'], max=Math.max(...ds.map(d=>data.hours[d]||0),1);
    return <>
      <div className="card" style={{background:'linear-gradient(135deg,var(--pink),var(--lav))'}}>
        <div style={{fontSize:'1.3rem',fontWeight:700}}>{greeting()}, Neko! 🌸</div>
        <div style={{fontSize:'.9rem',color:'#5a4a52'}}>{new Date().toLocaleDateString('en-US',{weekday:'long',month:'long',day:'numeric',year:'numeric'})}</div>
        <div style={{marginTop:10,fontStyle:'italic',fontSize:'.9rem',color:'#4a3a3f'}}>“{quote}”</div>
      </div>
      <div className="grid">
        <div className="card"><h3><i className="fas fa-check-circle"/> Daily Tasks</h3><div className="big">{pct}%</div><div className="bar"><div className="fill" style={{width:pct+'%'}}/></div><div style={{fontSize:'.85rem',color:'var(--muted)'}}>{done} of {tot} done</div></div>
        <div className="card"><h3><i className="fas fa-graduation-cap"/> Next Exam</h3><div className="big">{next?days(next.examDate):'—'}<span style={{fontSize:'1rem'}}> days</span></div><div style={{fontSize:'.9rem'}}>{next?next.code+' — '+fmt(next.examDate):'No exams'}</div></div>
        <div className="card"><h3><i className="fas fa-language"/> JLPT N5</h3><div className="big">{days(data.jlpt.examDate)}<span style={{fontSize:'1rem'}}> days</span></div><div style={{fontSize:'.9rem'}}>{fmt(data.jlpt.examDate)}</div><div style={{fontSize:'.8rem',color:'var(--muted)',marginTop:4}}>🔥 Streak: {data.jlpt.streak} days</div></div>
        <div className="card"><h3><i className="fas fa-calendar-alt"/> Upcoming Exams</h3>{upcoming.slice(0,4).map(s=><div key={s.id} className="between" style={{padding:'6px 0',borderBottom:'1px solid var(--border)'}}><span>{s.code}</span><span style={{fontSize:'.8rem',color:'var(--muted)'}}>{fmt(s.examDate)}</span></div>)}</div>
        <div className="card"><h3><i className="fas fa-clock"/> Today's Timetable</h3>{data.timetable.slice(0,5).map(t=><div key={t.id} className="between" style={{padding:'6px 0',borderBottom:'1px solid var(--border)'}}><span>{t.time}</span><span>{t.subject}</span><span className="badge">{t.type}</span></div>)}</div>
        <div className="card"><h3><i className="fas fa-bullseye"/> Daily Goals</h3><div style={{fontSize:'.9rem'}}>✔️ 2 semester topics</div><div style={{fontSize:'.9rem'}}>✔️ 20 JLPT flashcards</div><div style={{fontSize:'.9rem'}}>✔️ 1 Pomodoro session</div><div style={{fontSize:'.9rem'}}>✔️ Review mistakes</div></div>
        <div className="card" style={{gridColumn:'span 2'}}><h3><i className="fas fa-chart-bar"/> Weekly Study Progress (auto-logged from Pomodoro)</h3><div className="chart">{ds.map(d=><div key={d} className="col"><div className="bar-v" style={{height:((data.hours[d]||0)/max*100)+'%'}}/><div className="lbl">{d.toUpperCase()} · {data.hours[d]||0}h</div></div>)}</div></div>
      </div>
    </>;
  };

  // ================== SEMESTER ==================
  const unitPct=u=>{if(!u.topics.length)return 0;const d=u.topics.filter(t=>t.done).length;let p=d/u.topics.length*70;if(u.revised)p+=15;if(u.papers)p+=15;return Math.min(100,Math.round(p))};

  const Semester=()=>{
    if(subj){const s=data.subjects.find(x=>x.id===subj);
      return <><button className="btn sm" onClick={()=>setSubj(null)}><i className="fas fa-arrow-left"/> Back</button>
        <div className="card"><h3>{s.code} — {s.name}</h3><div style={{color:'var(--muted)',fontSize:'.9rem'}}>Exam: {fmt(s.examDate)} · {days(s.examDate)} days left</div></div>
        {s.units.map(u=>{const p=unitPct(u);return <div key={u.id} className="unit">
          <div className="between"><div style={{fontWeight:700}}>{u.name}</div><div style={{fontSize:'.8rem'}}>{p}%</div></div>
          <div className="bar"><div className="fill" style={{width:p+'%'}}/></div>

          {/* Subtopics editable */}
          <div style={{margin:'10px 0'}}>
            <div style={{fontWeight:600,fontSize:'.85rem',marginBottom:4}}>📖 Subtopics</div>
            <textarea rows="2" defaultValue={u.subtopics} onBlur={e=>upd(n=>{n.subjects.find(x=>x.id===subj).units.find(x=>x.id===u.id).subtopics=e.target.value})} style={{fontSize:'.8rem'}}/>
          </div>

          {/* Topics */}
          <div style={{margin:'10px 0'}}>
            <div style={{fontWeight:600,fontSize:'.85rem',marginBottom:6}}>📋 Topics</div>
            {u.topics.map(t=><div key={t.id} className="topic">
              <input type="checkbox" checked={t.done} onChange={()=>{
                const before=unitPct(u);
                upd(n=>{const uu=n.subjects.find(x=>x.id===subj).units.find(x=>x.id===u.id);uu.topics.find(x=>x.id===t.id).done=!t.done});
                if(!t.done && before<100){
                  setTimeout(()=>{const after=unitPct(data.subjects.find(x=>x.id===subj).units.find(x=>x.id===u.id));if(after===100){fireConfetti();show('Unit complete! 🎉')}},100);
                }
              }} style={{width:18,height:18,accentColor:'var(--pink-s)'}}/>
              <span style={t.done?{textDecoration:'line-through',color:'var(--muted)'}:{}}>{t.text}</span>
              <button className="btn danger sm" style={{marginLeft:'auto',padding:'2px 8px',fontSize:'.7rem'}} onClick={()=>{if(confirm('Delete topic?'))upd(n=>{const uu=n.subjects.find(x=>x.id===subj).units.find(x=>x.id===u.id);uu.topics=uu.topics.filter(x=>x.id!==t.id)})}}>✕</button>
            </div>)}
            <div className="flex" style={{marginTop:8}}><input placeholder="Add new topic..." id={'nt'+u.id} style={{flex:1,padding:'8px 12px',fontSize:'.8rem'}}/><button className="btn lav sm" onClick={()=>{const i=document.getElementById('nt'+u.id);if(!i.value.trim())return;upd(n=>{const uu=n.subjects.find(x=>x.id===subj).units.find(x=>x.id===u.id);uu.topics.push({id:uid(),text:i.value.trim(),done:false})});i.value=''}}>+</button></div>
          </div>

          {/* Important Questions editable */}
          <div style={{margin:'10px 0'}}>
            <div style={{fontWeight:600,fontSize:'.85rem',marginBottom:4}}>❓ Important Questions</div>
            {u.questions.map(q=><div key={q.id} className="q-row">
              <span className="q-mark">[{q.mark}m]</span>
              <span style={{flex:1}}>{q.text}</span>
              <button className="btn danger sm" style={{padding:'2px 8px',fontSize:'.7rem'}} onClick={()=>upd(n=>{const uu=n.subjects.find(x=>x.id===subj).units.find(x=>x.id===u.id);uu.questions=uu.questions.filter(x=>x.id!==q.id)})}>✕</button>
            </div>)}
            <div className="flex" style={{marginTop:6}}>
              <select id={'qm'+u.id} style={{width:80,padding:'6px 8px',fontSize:'.78rem'}}><option>2</option><option>5</option><option>8</option><option>10</option></select>
              <input id={'qt'+u.id} placeholder="Add question..." style={{flex:1,padding:'6px 10px',fontSize:'.8rem'}}/>
              <button className="btn lav sm" onClick={()=>{const m=document.getElementById('qm'+u.id).value;const t=document.getElementById('qt'+u.id);if(!t.value.trim())return;upd(n=>{const uu=n.subjects.find(x=>x.id===subj).units.find(x=>x.id===u.id);uu.questions.push({id:uid(),mark:+m,text:t.value.trim()})});t.value=''}}>+</button>
            </div>
          </div>

          {/* Unit notes */}
          <div style={{margin:'10px 0'}}>
            <div style={{fontWeight:600,fontSize:'.85rem',marginBottom:4}}>📝 Unit Notes</div>
            <textarea rows="2" defaultValue={u.notes} placeholder="Your notes..." onBlur={e=>upd(n=>{n.subjects.find(x=>x.id===subj).units.find(x=>x.id===u.id).notes=e.target.value})} style={{fontSize:'.8rem'}}/>
          </div>

          <div className="flex" style={{marginTop:8}}>
            <label style={{fontSize:'.8rem',display:'flex',alignItems:'center',gap:6}}><input type="checkbox" checked={u.papers} onChange={()=>upd(n=>{const uu=n.subjects.find(x=>x.id===subj).units.find(x=>x.id===u.id);uu.papers=!uu.papers})}/>Previous papers</label>
            <label style={{fontSize:'.8rem',display:'flex',alignItems:'center',gap:6}}><input type="checkbox" checked={u.revised} onChange={()=>upd(n=>{const uu=n.subjects.find(x=>x.id===subj).units.find(x=>x.id===u.id);uu.revised=!uu.revised})}/>Revised</label>
          </div>
        </div>})}
      </>;
    }
    return <><h2 style={{fontSize:'1.3rem',marginBottom:16}}><i className="fas fa-graduation-cap"/> Semester Planner</h2>
      <div className="grid">{data.subjects.map(s=>{const avg=Math.round(s.units.map(unitPct).reduce((a,b)=>a+b,0)/s.units.length);return <div key={s.id} className="card" style={{cursor:'pointer'}} onClick={()=>setSubj(s.id)}><div className="between"><div><div style={{fontWeight:700,fontSize:'1.1rem'}}>{s.code}</div><div style={{fontSize:'.8rem',color:'var(--muted)'}}>{s.name}</div></div><span className="badge">{fmt(s.examDate)}</span></div><div style={{marginTop:10}}><div className="between" style={{fontSize:'.8rem'}}><span>Completion</span><span>{avg}%</span></div><div className="bar"><div className="fill" style={{width:avg+'%'}}/></div></div></div>})}</div>
    </>;
  };

  // ================== JLPT (with quiz) ==================
  const startQuiz=type=>{
    const pool=[...HIRA,KATA].filter((_,i)=>i%2===0); // mix
    const chars=type==='hiragana'?HIRA:type==='katakana'?KATA:pool;
    const picked=[...chars].sort(()=>Math.random()-.5).slice(0,10);
    const qs=picked.map(c=>{
      const wrongs=chars.filter(x=>x[1]!==c[1]).sort(()=>Math.random()-.5).slice(0,3).map(x=>x[1]);
      const opts=[c[1],...wrongs].sort(()=>Math.random()-.5);
      return {char:c[0],answer:c[1],opts};
    });
    setQuiz({type,qs,idx:0,score:0,selected:null,done:false});
  };
  const answerQuiz=opt=>{
    if(quiz.selected!==null)return;
    const q=quiz.qs[quiz.idx];
    const correct=opt===q.answer;
    setQuiz({...quiz,selected:opt,score:quiz.score+(correct?1:0)});
    setTimeout(()=>{
      if(quiz.idx+1>=quiz.qs.length){
        const finalScore=quiz.score+(correct?1:0);
        // save score
        upd(n=>{n.jlpt.cats.Hiragana.quizzes.push(Math.round(finalScore/10*100));n.jlpt.cats.Hiragana.progress=Math.min(100,Math.round(n.jlpt.cats.Hiragana.quizzes.reduce((a,b)=>a+b,0)/n.jlpt.cats.Hiragana.quizzes.length))});
        setQuiz({...quiz,score:finalScore,selected:null,done:true,idx:quiz.idx});
      }else{
        setQuiz(q=>q?{...q,idx:q.idx+1,selected:null}:q);
      }
    },900);
  };

  const JLPT=()=>{
    const cats=data.jlpt.cats;const c=data.jlpt.flashcards[flashI%data.jlpt.flashcards.length];
    return <><div className="between" style={{marginBottom:16}}><h2 style={{fontSize:'1.3rem'}}><i className="fas fa-language"/> JLPT N5</h2><span className="badge">Exam: {fmt(data.jlpt.examDate)} · {days(data.jlpt.examDate)} days</span></div>

      <div className="card">
        <h3><i className="fas fa-question-circle"/> Kana Quiz</h3>
        {!quiz && <div className="flex"><button className="btn primary sm" onClick={()=>startQuiz('hiragana')}>Hiragana Quiz (10 Q)</button><button className="btn lav sm" onClick={()=>startQuiz('katakana')}>Katakana Quiz (10 Q)</button><button className="btn lav sm" onClick={()=>startQuiz('mixed')}>Mixed</button></div>}
        {quiz && !quiz.done && <>
          <div style={{fontSize:'.8rem',color:'var(--muted)',marginBottom:6}}>Question {quiz.idx+1} / {quiz.qs.length} · Score: {quiz.score}</div>
          <div className="quiz-q">{quiz.qs[quiz.idx].char}</div>
          {quiz.qs[quiz.idx].opts.map(o=>{
            let cls='quiz-opt';
            if(quiz.selected!==null){
              if(o===quiz.qs[quiz.idx].answer)cls+=' correct';
              else if(o===quiz.selected)cls+=' wrong';
            }
            return <button key={o} className={cls} onClick={()=>answerQuiz(o)} disabled={quiz.selected!==null}>{o}</button>;
          })}
        </>}
        {quiz && quiz.done && <>
          <div style={{textAlign:'center',padding:20}}>
            <div style={{fontSize:'2rem',fontWeight:700,color:'#b87b9a'}}>{quiz.score} / {quiz.qs.length}</div>
            <div style={{marginTop:8,color:'var(--muted)'}}>{quiz.score>=8?'Excellent! 🌸':quiz.score>=5?'Good job! Keep going 💪':'Keep practicing 🌱'}</div>
            <button className="btn primary sm" style={{marginTop:12}} onClick={()=>setQuiz(null)}>Try Again</button>
          </div>
        </>}
      </div>

      <div className="grid">
        <div className="card"><h3><i className="fas fa-layer-group"/> Vocabulary Flashcards</h3>
          <div className="flash" onClick={()=>setFlip(!flip)}><div className="jp">{flip?c.mn:c.jp}</div><div className="mn">{flip?'← click to flip':'Click to reveal meaning'}</div></div>
          <div className="flex" style={{marginTop:12,justifyContent:'center'}}><button className="btn lav sm" onClick={()=>{setFlashI((flashI-1+data.jlpt.flashcards.length)%data.jlpt.flashcards.length);setFlip(false)}}>← Prev</button><span style={{fontSize:'.8rem'}}>{flashI+1} / {data.jlpt.flashcards.length}</span><button className="btn lav sm" onClick={()=>{setFlashI((flashI+1)%data.jlpt.flashcards.length);setFlip(false)}}>Next →</button></div>
        </div>
        <div className="card"><h3><i className="fas fa-fire"/> Daily Streak</h3><div className="big">{data.jlpt.streak} 🔥</div>
          <button className="btn primary sm" onClick={()=>{const t=todayStr();if(data.jlpt.last===t){show('Already marked! 🌸');return}const y=new Date(Date.now()-864e5).toISOString().slice(0,10);upd(n=>{n.jlpt.streak=n.jlpt.last===y?n.jlpt.streak+1:1;n.jlpt.last=t});show('Streak updated! 🔥')}}>Mark studied today</button>
          <div style={{fontSize:'.8rem',color:'var(--muted)',marginTop:8}}>Last: {data.jlpt.last||'Never'}</div>
        </div>
        {Object.keys(cats).map(k=><div key={k} className="card"><div className="between"><div style={{fontWeight:700}}>{k}</div><div style={{fontSize:'.8rem'}}>{cats[k].progress}%</div></div><div className="bar"><div className="fill" style={{width:cats[k].progress+'%'}}/></div>
          <input type="range" min="0" max="100" value={cats[k].progress} onChange={e=>upd(n=>{n.jlpt.cats[k].progress=+e.target.value})} style={{marginTop:8}}/>
          <div style={{fontSize:'.8rem',marginTop:6}}><button className="btn lav sm" onClick={()=>{const s=prompt('Quiz score (0-100):');if(s!==null&&!isNaN(s)){upd(n=>{n.jlpt.cats[k].quizzes.push(+s);n.jlpt.cats[k].progress=Math.min(100,Math.round(n.jlpt.cats[k].quizzes.reduce((a,b)=>a+b,0)/n.jlpt.cats[k].quizzes.length))})}}}>📝 Record Quiz</button>{cats[k].quizzes.length?<span style={{marginLeft:8,fontSize:'.75rem'}}>Last: {cats[k].quizzes[cats[k].quizzes.length-1]}</span>:null}</div>
        </div>)}
      </div>

      <div className="card"><h3><i className="fas fa-book"/> Mistake Notebook</h3>
        {data.jlpt.mistakes.length?data.jlpt.mistakes.map((m,i)=><div key={i} className="between" style={{padding:'6px 0',borderBottom:'1px solid var(--border)'}}><span style={{fontSize:'.85rem'}}>{m}</span><button className="btn danger sm" onClick={()=>upd(n=>{n.jlpt.mistakes.splice(i,1)})}>✕</button></div>):<div style={{fontSize:'.85rem',color:'var(--muted)'}}>No mistakes recorded yet. 🌸</div>}
        <div className="flex" style={{marginTop:10}}><input id="mi" placeholder="Add a mistake..." style={{flex:1}}/><button className="btn lav sm" onClick={()=>{const i=document.getElementById('mi');if(i.value.trim()){upd(n=>n.jlpt.mistakes.push(i.value.trim()));i.value=''}}}>+ Add</button></div>
      </div>
    </>;
  };

  // ================== TODO ==================
  const Todo=()=>{let list=data.tasks;if(todoF==='done')list=list.filter(t=>t.done);if(todoF==='pending')list=list.filter(t=>!t.done);
    const tot=data.tasks.length, done=data.tasks.filter(t=>t.done).length, pct=tot?Math.round(done/tot*100):0;
    return <><div className="between" style={{marginBottom:16}}><h2 style={{fontSize:'1.3rem'}}><i className="fas fa-check-circle"/> Daily To-Do</h2><span className="badge">{done}/{tot} · {pct}%</span></div>
      <div className="bar" style={{marginBottom:16}}><div className="fill" style={{width:pct+'%'}}/></div>
      <div className="card"><div className="flex"><input id="nt" placeholder="Add a new task..." style={{flex:2}}/><select id="np" style={{flex:1}}><option value="low">Low</option><option value="medium" selected>Medium</option><option value="high">High</option></select><select id="nc" style={{flex:1}}><option>Semester</option><option>JLPT</option><option>General</option></select><input type="date" id="nd" style={{flex:1}}/><button className="btn primary sm" onClick={()=>{const t=document.getElementById('nt');if(!t.value.trim())return;upd(n=>n.tasks.push({id:uid(),text:t.value.trim(),done:false,priority:document.getElementById('np').value,due:document.getElementById('nd').value||'',category:document.getElementById('nc').value}));t.value=''}}>+ Add</button></div></div>
      <div className="flex" style={{marginBottom:16}}>{['all','pending','done'].map(f=><button key={f} className={'btn sm '+(todoF===f?'primary':'lav')} onClick={()=>setTodoF(f)}>{f[0].toUpperCase()+f.slice(1)}</button>)}</div>
      {list.length?list.map(t=><div key={t.id} className="task">
        <div className={'chk '+(t.done?'done':'')} onClick={()=>upd(n=>{const x=n.tasks.find(y=>y.id===t.id);x.done=!x.done})}>✓</div>
        <div className={t.done?'done-txt':''} style={{flex:1}}>{t.text}</div>
        <span className="badge">{t.priority}</span>
        <span className="badge" style={{background:'var(--bg)',border:'1px solid var(--border)'}}>{t.category}</span>
        {t.due && <span style={{fontSize:'.75rem',color:'var(--muted)'}}>{t.due}</span>}
        <button className="btn danger sm" onClick={()=>{if(confirm('Delete task?'))upd(n=>{n.tasks=n.tasks.filter(y=>y.id!==t.id)})}}>✕</button>
      </div>):<div style={{textAlign:'center',padding:40,color:'var(--muted)'}}>No tasks here. 🌸</div>}
    </>;
  };

  // ================== TIMETABLE (Pomodoro logs to chart) ==================
  const Timetable=()=>{
    return <>
      <h2 style={{fontSize:'1.3rem',marginBottom:16}}><i className="fas fa-clock"/> Timetable</h2>
      <div className="card">
        <h3><i className="fas fa-hourglass-half"/> Pomodoro Timer</h3>
        <div className="timer">{String(Math.floor(pomoSec/60)).padStart(2,'0')}:{String(pomoSec%60).padStart(2,'0')}</div>
        <div className="flex" style={{justifyContent:'center',marginTop:10}}>
          <select value={pomoTask} onChange={e=>setPomoTask(e.target.value)} style={{maxWidth:200}}>
            <option value="">No task linked</option>
            {data.tasks.filter(t=>!t.done).map(t=><option key={t.id} value={t.id}>{t.text}</option>)}
          </select>
        </div>
        <div className="flex" style={{justifyContent:'center',marginTop:12}}>
          <button className="btn primary sm" onClick={()=>setPomoOn(!pomoOn)}>{pomoOn?'Pause':'Start'}</button>
          <button className="btn lav sm" onClick={()=>{setPomoSec(1500);setPomoOn(false)}}>Reset</button>
          <button className="btn lav sm" onClick={()=>{logStudy(5);show('+5 min logged! 📚')}}>+5 min manual</button>
        </div>
        <div style={{fontSize:'.8rem',color:'var(--muted)',textAlign:'center',marginTop:8}}>
          Completed sessions auto-log 25 minutes to weekly study chart 📊
        </div>
      </div>

      <div className="card">
        <h3><i className="fas fa-list"/> Daily Schedule (10 AM – 11:30 PM)</h3>
        {data.timetable.map(t=><div key={t.id} className="slot">
          <span style={{fontWeight:600,minWidth:70,fontSize:'.85rem',color:'var(--muted)'}}>{t.time}</span>
          <input type="text" value={t.subject} onChange={e=>upd(n=>{n.timetable.find(x=>x.id===t.id).subject=e.target.value})} style={{flex:1,padding:'8px 12px',fontSize:'.85rem'}}/>
          <select value={t.type} onChange={e=>upd(n=>{n.timetable.find(x=>x.id===t.id).type=e.target.value})} style={{width:120,padding:'8px',fontSize:'.8rem'}}>
            {['Study','Break','Meal','JLPT','Revision','Practice Test'].map(type=><option key={type}>{type}</option>)}
          </select>
          <button className="btn danger sm" onClick={()=>upd(n=>{n.timetable=n.timetable.filter(x=>x.id!==t.id)})}>✕</button>
        </div>)}
        <div className="flex" style={{marginTop:12}}>
          <input type="time" id="nst" style={{width:120}}/>
          <input type="text" id="nss" placeholder="Subject" style={{flex:1}}/>
          <button className="btn lav sm" onClick={()=>{const tm=document.getElementById('nst').value,su=document.getElementById('nss').value;if(!tm||!su)return;upd(n=>{n.timetable.push({id:uid(),time:tm,subject:su,type:'Study'});n.timetable.sort((a,b)=>a.time.localeCompare(b.time))});document.getElementById('nst').value='';document.getElementById('nss').value=''}}>+ Add Slot</button>
        </div>
      </div>
    </>;
  };

  // ================== CALENDAR ==================
  const Calendar=()=>{
    const y=cal.getFullYear(),m=cal.getMonth();
    const first=new Date(y,m,1),last=new Date(y,m+1,0),startDay=first.getDay(),daysInMonth=last.getDate();
    const byDate={};data.events.forEach(e=>{if(!byDate[e.date])byDate[e.date]=[];byDate[e.date].push(e)});
    const monthNames=['January','February','March','April','May','June','July','August','September','October','November','December'];
    const dayNames=['Sun','Mon','Tue','Wed','Thu','Fri','Sat'];
    let cells=[];
    for(let i=0;i<startDay;i++)cells.push(<div key={'e'+i} className="day off"></div>);
    for(let d=1;d<=daysInMonth;d++){
      const ds=`${y}-${String(m+1).padStart(2,'0')}-${String(d).padStart(2,'0')}`;
      const has=!!byDate[ds],isToday=ds===todayStr();
      cells.push(<div key={d} className={'day '+(has?'has ':'')+(isToday?'today':'')} title={has?byDate[ds].map(e=>e.title).join(', '):''} onClick={()=>{if(has)show(byDate[ds].map(e=>e.title).join(' · '))}}>{d}</div>);
    }
    return <>
      <div className="between" style={{marginBottom:16}}><h2 style={{fontSize:'1.3rem'}}><i className="fas fa-calendar-alt"/> Calendar</h2>
        <div className="flex"><button className="btn lav sm" onClick={()=>setCal(new Date(y,m-1,1))}>←</button><span style={{fontWeight:700}}>{monthNames[m]} {y}</span><button className="btn lav sm" onClick={()=>setCal(new Date(y,m+1,1))}>→</button></div>
      </div>
      <div className="card"><div className="cal">{dayNames.map(d=><div key={d} style={{textAlign:'center',fontSize:'.7rem',fontWeight:700,color:'var(--muted)'}}>{d}</div>)}{cells}</div></div>
      <div className="card"><h3><i className="fas fa-calendar-plus"/> Add Event</h3>
        <div className="flex"><input type="date" id="ed" style={{flex:1}}/><input type="text" id="et" placeholder="Event title" style={{flex:2}}/><select id="ety" style={{flex:1}}><option value="exam">Exam</option><option value="revision">Revision</option><option value="deadline">Deadline</option><option value="jlpt">JLPT</option></select><button className="btn primary sm" onClick={()=>{const d=document.getElementById('ed').value,t=document.getElementById('et').value;if(!d||!t)return;upd(n=>n.events.push({id:uid(),date:d,title:t,type:document.getElementById('ety').value}));document.getElementById('ed').value='';document.getElementById('et').value=''}}>+ Add</button></div>
      </div>
      <div className="card"><h3><i className="fas fa-list"/> All Events</h3>
        {data.events.sort((a,b)=>a.date.localeCompare(b.date)).map(e=><div key={e.id} className="between" style={{padding:'6px 0',borderBottom:'1px solid var(--border)'}}><div><span className="badge" style={{marginRight:8}}>{e.type}</span><span style={{fontSize:'.88rem'}}>{e.title}</span></div><div className="flex" style={{gap:6}}><span style={{fontSize:'.78rem',color:'var(--muted)'}}>{fmt(e.date)}</span><button className="btn danger sm" style={{padding:'2px 8px',fontSize:'.7rem'}} onClick={()=>{if(confirm('Delete event?'))upd(n=>{n.events=n.events.filter(x=>x.id!==e.id)})}}>✕</button></div></div>)}
      </div>
    </>;
  };

  // ================== PROGRESS ==================
  const Progress=()=>{
    const sp=data.subjects.map(s=>({code:s.code,pct:Math.round(s.units.map(unitPct).reduce((a,b)=>a+b,0)/s.units.length)}));
    const overallSem=Math.round(sp.reduce((a,b)=>a+b.pct,0)/sp.length);
    const jp=Object.entries(data.jlpt.cats).map(([k,v])=>({cat:k,pct:v.progress}));
    const overallJLPT=Math.round(jp.reduce((a,b)=>a+b.pct,0)/jp.length);
    const ds=['mon','tue','wed','thu','fri','sat','sun'],max=Math.max(...ds.map(d=>data.hours[d]||0),1);
    return <>
      <h2 style={{fontSize:'1.3rem',marginBottom:16}}><i className="fas fa-chart-line"/> Progress Analytics</h2>
      <div className="grid">
        <div className="card"><h3><i className="fas fa-graduation-cap"/> Semester Overall</h3><div className="big">{overallSem}%</div><div className="bar"><div className="fill" style={{width:overallSem+'%'}}/></div></div>
        <div className="card"><h3><i className="fas fa-language"/> JLPT Overall</h3><div className="big">{overallJLPT}%</div><div className="bar"><div className="fill" style={{width:overallJLPT+'%'}}/></div></div>
        <div className="card"><h3><i className="fas fa-book"/> Subject Progress</h3>{sp.map(s=><div key={s.code} style={{margin:'6px 0'}}><div className="between" style={{fontSize:'.8rem'}}><span>{s.code}</span><span>{s.pct}%</span></div><div className="bar" style={{height:8}}><div className="fill" style={{width:s.pct+'%'}}/></div></div>)}</div>
        <div className="card"><h3><i className="fas fa-flag"/> JLPT Categories</h3>{jp.map(j=><div key={j.cat} style={{margin:'6px 0'}}><div className="between" style={{fontSize:'.8rem'}}><span>{j.cat}</span><span>{j.pct}%</span></div><div className="bar" style={{height:8}}><div className="fill" style={{width:j.pct+'%'}}/></div></div>)}</div>
        <div className="card" style={{gridColumn:'span 2'}}><h3><i className="fas fa-clock"/> Weekly Study Hours (auto-logged)</h3>
          <div className="chart">{ds.map(d=><div key={d} className="col"><div className="bar-v" style={{height:((data.hours[d]||0)/max*100)+'%'}}/><div className="lbl">{d.toUpperCase()} · {data.hours[d]||0}h</div></div>)}</div>
        </div>
        <div className="card" style={{gridColumn:'span 2'}}><h3><i className="fas fa-file-export"/> Export Report</h3>
          <div className="flex"><button className="btn primary sm" onClick={()=>{const json=JSON.stringify(data,null,2);const b=new Blob([json],{type:'application/json'});const a=document.createElement('a');a.href=URL.createObjectURL(b);a.download='studyneko-'+todayStr()+'.json';a.click()}}>Download JSON backup</button>
          <button className="btn lav sm" onClick={()=>window.print()}>Print / Save PDF</button></div>
        </div>
      </div>
    </>;
  };

  // ================== NOTES (grouped) ==================
  const Notes=()=>{
    const groups=['Semester','JLPT','General'];
    return <>
      <h2 style={{fontSize:'1.3rem',marginBottom:16}}><i className="fas fa-sticky-note"/> Notes</h2>
      <div className="card"><div className="flex"><input id="ni" placeholder="Note title" style={{flex:2}}/><select id="nic" style={{flex:1}}><option>Semester</option><option>JLPT</option><option>General</option></select><button className="btn primary sm" onClick={()=>{const t=document.getElementById('ni');if(!t.value.trim())return;upd(n=>n.notes.push({id:uid(),title:t.value.trim(),content:'',category:document.getElementById('nic').value}));t.value=''}}>+ Add Note</button></div></div>
      {groups.map(g=>{const ns=data.notes.filter(n=>(n.category||'General')===g);if(!ns.length)return null;return <div key={g} className="card"><h3>{g}</h3>{ns.map(n=><div key={n.id} style={{background:'var(--bg)',borderRadius:14,padding:14,marginBottom:10,border:'1px solid var(--border)'}}><div className="between"><div style={{fontWeight:700}}>{n.title}</div><button className="btn danger sm" style={{padding:'2px 8px',fontSize:'.7rem'}} onClick={()=>{if(confirm('Delete note?'))upd(x=>{x.notes=x.notes.filter(y=>y.id!==n.id)})}}>✕</button></div><textarea rows="2" defaultValue={n.content} onBlur={e=>upd(x=>{x.notes.find(y=>y.id===n.id).content=e.target.value})} style={{marginTop:8,fontSize:'.85rem'}}/></div>)}</div>})}
    </>;
  };

  // ================== SETTINGS ==================
  const Settings=()=>{
    const fileRef=useRef();
    return <>
      <h2 style={{fontSize:'1.3rem',marginBottom:16}}><i className="fas fa-cog"/> Settings</h2>
      <div className="grid">
        <div className="card"><h3><i className="fas fa-palette"/> Appearance</h3><button className="btn primary" onClick={()=>upd(n=>n.theme=n.theme==='dark'?'light':'dark')}>Toggle Light / Dark</button></div>
        <div className="card"><h3><i className="fas fa-database"/> Data Management</h3>
          <div className="flex">
            <button className="btn primary sm" onClick={()=>{const b=new Blob([JSON.stringify(data,null,2)],{type:'application/json'});const a=document.createElement('a');a.href=URL.createObjectURL(b);a.download='studyneko-'+todayStr()+'.json';a.click()}}>Export</button>
            <button className="btn lav sm" onClick={()=>fileRef.current.click()}>Import</button>
            <input type="file" ref={fileRef} accept=".json" style={{display:'none'}} onChange={e=>{const f=e.target.files[0];if(!f)return;const r=new FileReader();r.onload=ev=>{try{const parsed=JSON.parse(ev.target.result);setData(merge(defaults(),parsed));show('Data imported! 🌸')}catch(err){show('Invalid file')}};r.readAsText(f)}}/>
            <button className="btn danger sm" onClick={()=>{if(confirm('Reset ALL data? This cannot be undone.')){localStorage.removeItem(KEY);setData(defaults());show('Reset complete')}}}>Reset</button>
          </div>
        </div>
        <div className="card"><h3><i className="fas fa-quote-left"/> Quotes</h3>{data.quotes.map((q,i)=><div key={i} style={{fontSize:'.85rem',padding:'4px 0'}}>“{q}”</div>)}</div>
        <div className="card"><h3><i className="fas fa-info-circle"/> About</h3><div style={{fontSize:'.85rem'}}>StudyNeko v2.0 — B.Tech AI & JLPT N5 planner.</div><div style={{fontSize:'.85rem',marginTop:6}}>Small Steps, Big Dreams 🌸</div></div>
      </div>
    </>;
  };

  // ================== SEARCH ==================
  const Search=()=>{
    const q=search.toLowerCase().trim();
    if(!q)return null;
    const results=[];
    data.tasks.forEach(t=>{if(t.text.toLowerCase().includes(q))results.push({type:'Task',text:t.text,page:'todo'})});
    data.subjects.forEach(s=>{if(s.code.toLowerCase().includes(q)||s.name.toLowerCase().includes(q))results.push({type:'Subject',text:s.code+' — '+s.name,page:'semester',subj:s.id});s.units.forEach(u=>{u.topics.forEach(t=>{if(t.text.toLowerCase().includes(q))results.push({type:'Topic',text:s.code+' › '+u.name+' › '+t.text,page:'semester',subj:s.id})})})});
    data.notes.forEach(n=>{if(n.title.toLowerCase().includes(q)||n.content.toLowerCase().includes(q))results.push({type:'Note',text:n.title,page:'notes'})});
    data.events.forEach(e=>{if(e.title.toLowerCase().includes(q))results.push({type:'Event',text:e.title+' ('+fmt(e.date)+')',page:'calendar'})});
    data.jlpt.flashcards.forEach(f=>{if(f.jp.includes(q)||f.mn.toLowerCase().includes(q))results.push({type:'Flashcard',text:f.jp+' — '+f.mn,page:'jlpt'})});

    return <div className="card"><h3><i className="fas fa-search"/> Results ({results.length})</h3><div className="search-results">
      {results.length===0 && <div style={{color:'var(--muted)',fontSize:'.9rem'}}>No matches for "{search}"</div>}
      {results.slice(0,30).map((r,i)=><div key={i} className="search-item" onClick={()=>{setPage(r.page);if(r.subj)setSubj(r.subj);setSearch('')}}><div className="search-type">{r.type}</div><div style={{fontSize:'.9rem'}}>{r.text}</div></div>)}
    </div></div>;
  };

  // ================== NAV & RENDER ==================
  const pages=['dashboard','semester','jlpt','todo','timetable','calendar','progress','notes','settings'];
  const labels={dashboard:'Dashboard',semester:'Semester',jlpt:'JLPT N5',todo:'To-Do',timetable:'Timetable',calendar:'Calendar',progress:'Progress',notes:'Notes',settings:'Settings'};
  const icons={dashboard:'home',semester:'graduation-cap',jlpt:'language',todo:'check-circle',timetable:'clock',calendar:'calendar-alt',progress:'chart-line',notes:'sticky-note',settings:'cog'};

  return <>
    <Confetti/>
    <header>
      <div><div className="logo">🌸 StudyNeko</div><div className="tag">Small Steps, Big Dreams 🌸</div></div>
      <div className="flex">
        <button className="btn sm" onClick={()=>upd(n=>n.theme=n.theme==='dark'?'light':'dark')}><i className={'fas fa-'+(data.theme==='dark'?'sun':'moon')}/></button>
      </div>
    </header>

    <div className="searchbar">
      <input className="search-input" placeholder="🔍 Search tasks, topics, notes, events, kanji..." value={search} onChange={e=>setSearch(e.target.value)}/>
      {search && <button className="btn sm" onClick={()=>setSearch('')}>✕</button>}
    </div>

    {search ? <Search/> : <>
      <nav><div className="nav">
        {pages.map(p=><button key={p} className={'btn sm '+(page===p?'active':'')} onClick={()=>{setPage(p);setSubj(null)}}><i className={'fas fa-'+icons[p]}/> {labels[p]}</button>)}
      </div></nav>

      {page==='dashboard'&&<Dashboard/>}
      {page==='semester'&&<Semester/>}
      {page==='jlpt'&&<JLPT/>}
      {page==='todo'&&<Todo/>}
      {page==='timetable'&&<Timetable/>}
      {page==='calendar'&&<Calendar/>}
      {page==='progress'&&<Progress/>}
      {page==='notes'&&<Notes/>}
      {page==='settings'&&<Settings/>}
    </>}
    {toast && <div className="toast">{toast}</div>}
  </>;
}

ReactDOM.createRoot(document.getElementById('root')).render(<App/>);
</script>
</body>
</html>
