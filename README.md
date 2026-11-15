# 6-JornadaAcademica-Nassau
<!doctype html>
<html lang="pt-BR">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>6ª Jornada Acadêmica UNINASSAU</title>
<style>
:root{--bg:#f4f7ff;--sf:#fff;--tx:#10213f;--mu:#56668a;--bl:#0b3d91;--bd:#d3dcf0;--er:#b3261e;--ok:#17703a;--ye:#ffc400;color-scheme:light;box-sizing:border-box;padding-top:env(safe-area-inset-top,0px);padding-bottom:env(safe-area-inset-bottom,0px)}
@media (prefers-color-scheme:dark){:root:not([data-theme="light"]){--bg:#0c1426;--sf:#142040;--tx:#eaf0ff;--mu:#9fb0d3;--bd:#2a3a64;--er:#ff8a80;--ok:#6fdc8c;color-scheme:dark}}
:root[data-theme="dark"]{--bg:#0c1426;--sf:#142040;--tx:#eaf0ff;--mu:#9fb0d3;--bd:#2a3a64;--er:#ff8a80;--ok:#6fdc8c;color-scheme:dark}
*,*::before,*::after{box-sizing:inherit}
html{scroll-padding-top:env(safe-area-inset-top,0px)}
body{margin:0;background:var(--bg);color:var(--tx);font:16px/1.55 "Segoe UI",system-ui,-apple-system,Roboto,sans-serif}
button,input,select{font-family:inherit}
header{background:#0b3d91;color:#fff;border-bottom:6px solid var(--ye);padding:14px 20px}
.top{max-width:960px;margin:0 auto;display:flex;flex-wrap:wrap;align-items:center;gap:12px 24px;justify-content:space-between}
.logo{font-weight:800;font-size:20px;letter-spacing:.2px}.logo b{color:var(--ye)}
nav{display:flex;gap:4px;flex-wrap:wrap}
nav button{background:transparent;color:#dbe6ff;border:0;border-bottom:3px solid transparent;padding:8px 12px;font-size:15px;font-weight:600;cursor:pointer}
nav button[aria-selected="true"]{color:#fff;border-bottom-color:var(--ye)}
button:focus-visible,input:focus-visible,select:focus-visible,a:focus-visible{outline:3px solid var(--ye);outline-offset:2px}
main{max-width:960px;margin:0 auto;padding:24px 20px 48px}
section[hidden]{display:none}
h1{font-size:clamp(30px,6vw,52px);line-height:1.08;margin:8px 0 14px;color:var(--bl)}
:root[data-theme="dark"] h1{color:var(--ye)}
@media (prefers-color-scheme:dark){:root:not([data-theme="light"]) h1{color:var(--ye)}}
h2{margin:0 0 12px;font-size:24px}
.lead{color:var(--mu);max-width:60ch;font-size:18px}
.days{display:grid;grid-template-columns:repeat(auto-fit,minmax(130px,1fr));gap:10px;margin:22px 0}
.day{background:var(--sf);border:1px solid var(--bd);border-left:5px solid var(--ye);padding:10px 12px;border-radius:6px}
.day b{display:block}.day span{color:var(--mu);font-size:14px}
.card{background:var(--sf);border:1px solid var(--bd);border-radius:8px;padding:20px}
.grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(240px,1fr));gap:14px}
label{display:block;font-weight:600;font-size:14px;margin-bottom:4px}
input,select{width:100%;padding:10px 12px;border:1px solid var(--bd);border-radius:6px;background:var(--bg);color:var(--tx);font-size:16px}
input[aria-invalid="true"],select[aria-invalid="true"]{border-color:var(--er)}
.err{display:block;color:var(--er);font-size:13px;min-height:18px}
.btn{background:var(--ye);color:#10213f;border:0;border-radius:6px;padding:12px 22px;font-size:16px;font-weight:700;cursor:pointer}
.btn:disabled{opacity:.6;cursor:wait}
.btn.sec{background:transparent;color:var(--tx);border:1px solid var(--bd)}
.msg{margin-top:14px;padding:10px 14px;border-radius:6px;border:1px solid var(--bd)}
.msg.ok{color:var(--ok);border-color:var(--ok)}.msg.bad{color:var(--er);border-color:var(--er)}
.wrap{overflow-x:auto}
table{border-collapse:collapse;width:100%;min-width:520px}
th,td{padding:8px 10px;border-bottom:1px solid var(--bd);text-align:left}
td.c,th.c{text-align:center}
input[type=checkbox]{width:22px;height:22px;accent-color:#0b3d91}
.row{display:flex;gap:10px;flex-wrap:wrap;margin-top:14px}
.empty{color:var(--mu)}
</style>
</head>
<body>
<header><div class="top">
<div class="logo">6ª Jornada <b>Acadêmica</b> UNINASSAU</div>
<nav role="tablist" aria-label="Seções">
<button role="tab" data-t="inicio" aria-selected="true">Início</button>
<button role="tab" data-t="inscricao" aria-selected="false">Inscrição</button>
<button role="tab" data-t="checkin" aria-selected="false">Check-in</button>
<button role="tab" data-t="certificado" aria-selected="false">Certificado</button>
</nav></div></header>
<main>
<section id="inicio">
<h1>Inscreva-se na 6ª Jornada Acadêmica</h1>
<p class="lead">Cinco dias de palestras, oficinas e tecnologia. Quem participar de 20 horas recebe o certificado por e-mail.</p>
<div class="days" id="dias"></div>
<div class="row"><button class="btn" data-go="inscricao">Fazer inscrição</button><button class="btn sec" id="demo">Carregar dados de teste</button></div>
<p class="empty" id="demoMsg"></p>
</section>

<section id="inscricao" hidden>
<h2>Inscrição</h2>
<form id="f" class="card" novalidate>
<div class="grid">
<div><label for="nome">Nome completo</label><input id="nome" autocomplete="name"><span class="err"></span></div>
<div><label for="email">E-mail</label><input id="email" type="email" autocomplete="email"><span class="err"></span></div>
<div><label for="tel">Telefone</label><input id="tel" inputmode="numeric" placeholder="(86) 99999-9999"><span class="err"></span></div>
<div><label for="cpf">CPF</label><input id="cpf" inputmode="numeric" placeholder="000.000.000-00"><span class="err"></span></div>
<div><label for="mat">Matrícula</label><input id="mat" inputmode="numeric" maxlength="10"><span class="err"></span></div>
<div><label for="curso">Curso</label><select id="curso"><option value="">Selecione</option><option>Análise e Desenvolvimento de Sistemas</option><option>Ciência da Computação</option><option>Engenharia de Software</option><option>Sistemas de Informação</option><option>Outro</option></select><span class="err"></span></div>
</div>
<div class="row"><button class="btn" id="salvar" type="submit">Salvar inscrição</button></div>
<div id="fmsg" role="status"></div>
</form>
</section>

<section id="checkin" hidden>
<h2>Painel de frequência</h2>
<p class="lead">Marque os dias em que cada aluno esteve presente. Cada dia vale 4 horas.</p>
<div class="card wrap" id="painel"></div>
</section>

<section id="certificado" hidden>
<h2>Certificado</h2>
<div class="card">
<label for="ccpf">Informe seu CPF</label>
<input id="ccpf" inputmode="numeric" placeholder="000.000.000-00" style="max-width:280px">
<div class="row"><button class="btn" id="gerar">Gerar certificado</button></div>
<div id="cmsg" role="status"></div>
</div>
</section>
</main>

<script src="https://cdnjs.cloudflare.com/ajax/libs/jspdf/2.5.1/jspdf.umd.min.js"></script>
<script>
const $=s=>document.querySelector(s), $$=s=>[...document.querySelectorAll(s)];
const DIAS=5, HPD=4, MIN=20;
const mem={};
const ld=(k,d)=>{try{const v=localStorage.getItem(k);if(v)return JSON.parse(v)}catch(e){}return k in mem?mem[k]:d};
const sv=(k,v)=>{mem[k]=v;try{localStorage.setItem(k,JSON.stringify(v))}catch(e){}};
const dig=s=>s.replace(/\D/g,'');
const esc=s=>s.replace(/[&<>"]/g,c=>({'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;'}[c]));
const mCPF=v=>{v=dig(v).slice(0,11);if(v.length>9)return v.replace(/(\d{3})(\d{3})(\d{3})(\d{1,2})/,'$1.$2.$3-$4');if(v.length>6)return v.replace(/(\d{3})(\d{3})(\d{1,3})/,'$1.$2.$3');if(v.length>3)return v.replace(/(\d{3})(\d{1,3})/,'$1.$2');return v};
const mTel=v=>{v=dig(v).slice(0,11);if(v.length>10)return v.replace(/(\d{2})(\d{5})(\d{4})/,'($1) $2-$3');if(v.length>6)return v.replace(/(\d{2})(\d{4})(\d{1,4})/,'($1) $2-$3');if(v.length>2)return v.replace(/(\d{2})(\d{1,5})/,'($1) $2');return v};
function cpfOk(c){c=dig(c);if(c.length!==11||/^(\d)\1+$/.test(c))return false;for(let t=9;t<11;t++){let s=0;for(let i=0;i<t;i++)s+=c[i]*(t+1-i);if((s*10%11)%10!=c[t])return false}return true}

// Navegação
function go(t){$$('section').forEach(s=>s.hidden=s.id!==t);$$('nav button').forEach(b=>b.setAttribute('aria-selected',b.dataset.t===t));if(t==='checkin')painel()}
$$('nav button').forEach(b=>b.onclick=()=>go(b.dataset.t));
$$('[data-go]').forEach(b=>b.onclick=()=>go(b.dataset.go));
$('#dias').innerHTML=Array.from({length:DIAS},(_,i)=>`<div class="day"><b>Dia ${i+1}</b><span>${HPD} horas</span></div>`).join('');

// Máscaras
$('#cpf').oninput=e=>e.target.value=mCPF(e.target.value);
$('#ccpf').oninput=e=>e.target.value=mCPF(e.target.value);
$('#tel').oninput=e=>e.target.value=mTel(e.target.value);
$('#mat').oninput=e=>e.target.value=dig(e.target.value);

// Inscrição (bloqueia CPF e e-mail duplicados)
function erro(id,m){const el=$('#'+id);el.setAttribute('aria-invalid',m?'true':'false');el.parentNode.querySelector('.err').textContent=m||'';return !m}
$('#f').onsubmit=e=>{
  e.preventDefault();
  const btn=$('#salvar'); if(btn.disabled)return; btn.disabled=true;
  const v={nome:$('#nome').value.trim().replace(/\s+/g,' '),email:$('#email').value.trim().toLowerCase(),tel:$('#tel').value,cpf:$('#cpf').value,mat:$('#mat').value,curso:$('#curso').value};
  const alunos=ld('sgja:alunos',[]);
  const ok=[
    erro('nome',v.nome.split(' ').length>1&&v.nome.length>=5?'':'Informe nome e sobrenome.'),
    erro('email',/^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(v.email)?'':'Informe um e-mail válido.'),
    erro('tel',dig(v.tel).length>=10?'':'Informe DDD e número.'),
    erro('cpf',!cpfOk(v.cpf)?'CPF inválido.':alunos.some(a=>dig(a.cpf)===dig(v.cpf))?'Este CPF já está inscrito.':''),
    erro('mat',v.mat.length>=6?'':'A matrícula deve ter ao menos 6 dígitos.'),
    erro('curso',v.curso?'':'Selecione o curso.')
  ];
  if(!alunos.every(a=>a.email!==v.email)){erro('email','Este e-mail já está inscrito.');ok.push(false)}
  const m=$('#fmsg');
  if(ok.includes(false)){m.className='msg bad';m.textContent='Corrija os campos destacados.';btn.disabled=false;return}
  alunos.push(v);sv('sgja:alunos',alunos);
  m.className='msg ok';m.textContent='Inscrição salva. Nos vemos na Jornada!';
  $('#f').reset();btn.disabled=false;
};

// Check-in
function painel(){
  const al=ld('sgja:alunos',[]), fr=ld('sgja:freq',{});
  if(!al.length){$('#painel').innerHTML='<p class="empty">Nenhum aluno inscrito ainda. Faça uma inscrição para começar a chamada.</p>';return}
  $('#painel').innerHTML='<table><thead><tr><th>Aluno</th>'+Array.from({length:DIAS},(_,i)=>`<th class="c">D${i+1}</th>`).join('')+'<th class="c">Horas</th></tr></thead><tbody>'+
  al.map(a=>{const k=dig(a.cpf),p=fr[k]||[];const h=p.filter(Boolean).length*HPD;
    return `<tr><td>${esc(a.nome)}</td>`+Array.from({length:DIAS},(_,i)=>`<td class="c"><input type="checkbox" aria-label="${esc(a.nome)}, dia ${i+1}" data-k="${k}" data-d="${i}" ${p[i]?'checked':''}></td>`).join('')+`<td class="c" id="h${k}"><b>${h}h</b></td></tr>`}).join('')+'</tbody></table>';
  $$('#painel input').forEach(c=>c.onchange=()=>{
    const f=ld('sgja:freq',{});const p=f[c.dataset.k]||Array(DIAS).fill(false);p[c.dataset.d]=c.checked;f[c.dataset.k]=p;sv('sgja:freq',f);
    $('#h'+c.dataset.k).innerHTML='<b>'+p.filter(Boolean).length*HPD+'h</b>';
  });
}

// Certificado (mínimo 20h)
$('#gerar').onclick=()=>{
  const m=$('#cmsg'), k=dig($('#ccpf').value);
  const a=ld('sgja:alunos',[]).find(x=>dig(x.cpf)===k);
  if(!a){m.className='msg bad';m.textContent='CPF não encontrado. Confira o número ou faça a inscrição.';return}
  const h=(ld('sgja:freq',{})[k]||[]).filter(Boolean).length*HPD;
  if(h<MIN){m.className='msg bad';m.textContent=`Você tem ${h}h de presença. O certificado exige ${MIN}h.`;return}
  pdf(a,h);
  const corpo=encodeURIComponent(`Olá, ${a.nome}!\n\nObrigado por participar da 6ª Jornada Acadêmica da UNINASSAU. Seu certificado de ${h} horas está em anexo.\n\nEquipe da Jornada Acadêmica`);
  m.className='msg ok';
  m.innerHTML=`Certificado de ${h}h gerado. <a href="mailto:${esc(a.email)}?subject=${encodeURIComponent('Seu certificado - 6ª Jornada Acadêmica')}&body=${corpo}">Abrir e-mail para enviar</a>`;
};
function pdf(a,h){
  const d=new window.jspdf.jsPDF({orientation:'landscape',unit:'pt',format:'a4'});
  const W=d.internal.pageSize.getWidth(),H=d.internal.pageSize.getHeight();
  d.setFillColor(11,61,145);d.rect(0,0,W,H,'F');
  d.setFillColor(255,255,255);d.rect(18,18,W-36,H-36,'F');
  d.setFillColor(255,196,0);d.rect(18,18,W-36,16,'F');d.rect(18,H-34,W-36,16,'F');
  d.setTextColor(11,61,145);d.setFont('helvetica','bold');d.setFontSize(44);d.text('CERTIFICADO',W/2,130,{align:'center'});
  d.setTextColor(16,33,63);d.setFont('helvetica','normal');d.setFontSize(16);d.text('Certificamos que',W/2,190,{align:'center'});
  d.setFont('helvetica','bold');d.setFontSize(30);d.text(a.nome,W/2,240,{align:'center',maxWidth:W-120});
  d.setFont('helvetica','normal');d.setFontSize(16);
  d.text(d.splitTextToSize(`participou da 6ª Jornada Acadêmica da UNINASSAU, curso de ${a.curso}, com carga horária total de ${h} horas.`,W-200),W/2,290,{align:'center'});
  d.setDrawColor(11,61,145);d.line(W/2-120,H-100,W/2+120,H-100);d.setFontSize(12);d.text('Coordenação da Jornada Acadêmica',W/2,H-82,{align:'center'});
  d.save('certificado-'+a.nome.split(' ')[0].toLowerCase()+'.pdf');
}

// Dados de teste para a demonstração
$('#demo').onclick=()=>{
  const al=[{nome:'Ana Souza Lima',email:'ana@teste.com',tel:'(86) 99999-0001',cpf:'529.982.247-25',mat:'20261001',curso:'Análise e Desenvolvimento de Sistemas'},{nome:'Bruno Alves Costa',email:'bruno@teste.com',tel:'(86) 99999-0002',cpf:'111.444.777-35',mat:'20261002',curso:'Engenharia de Software'}];
  sv('sgja:alunos',al);sv('sgja:freq',{'52998224725':[true,true,true,true,true],'11144477735':[true,true,false,false,false]});
  $('#demoMsg').textContent='Dados de teste carregados: Ana (20h, recebe certificado) e Bruno (8h, não recebe). CPFs: 529.982.247-25 e 111.444.777-35.';
};
</script>
</body>
</html>
