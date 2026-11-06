<!DOCTYPE html>
<html lang="bn">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1">
<title>SPY NAME STUDIO</title>
<style>
*{box-sizing:border-box}body{margin:0;padding:18px;background:radial-gradient(circle at top,#1b3158,#080d18 65%);font-family:Arial,sans-serif;color:#eef5ff}
.wrap{max-width:540px;margin:auto}.brand{text-align:center;color:#45eaff;font-size:27px;font-weight:900;letter-spacing:2px;margin:12px 0 4px;text-shadow:0 0 18px #45eaff66}.sub{text-align:center;color:#9db3d2;font-size:11px;margin-bottom:18px}
.panel{background:#111d32;border:1px solid #2d4264;border-radius:17px;padding:15px;margin:12px 0;box-shadow:0 10px 28px #0005}
.tabs{display:grid;grid-template-columns:repeat(3,1fr);gap:7px}.tab{background:#1b2b45;color:#dceaff;border:1px solid #3a5276;border-radius:10px;padding:11px 3px;font-weight:700}.tab.active{background:linear-gradient(120deg,#0daec6,#7756d9);border-color:transparent;color:white}
label{display:block;color:#b9cce5;font-size:13px;margin:13px 0 7px}input[type=text]{width:100%;padding:13px;border-radius:10px;border:1px solid #405a7e;background:#081321;color:white;font-size:16px}
.actions{display:flex;gap:9px;margin-top:11px}.btn{flex:1;padding:13px 8px;border:0;border-radius:10px;background:linear-gradient(120deg,#37e4f4,#8b79ff);font-weight:800;color:#07111d}.btn.alt{background:#263954;color:#eef6ff;border:1px solid #435b7d}.btn.copy{background:linear-gradient(120deg,#ff5bd0,#ffad61);color:#21091b}
.switchrow{display:flex;align-items:center;justify-content:space-between;margin-top:14px;font-size:14px;color:#d9e8fa}.switch{width:46px;height:25px;position:relative}.switch input{display:none}.slider{position:absolute;inset:0;background:#43516a;border-radius:30px}.slider:before{content:"";position:absolute;width:19px;height:19px;left:3px;top:3px;border-radius:50%;background:white;transition:.2s}.switch input:checked+.slider{background:#0bb4c9}.switch input:checked+.slider:before{transform:translateX(21px)}
.small{color:#9db1cd;font-size:12px;margin-bottom:8px}.result{min-height:70px;display:flex;align-items:center;justify-content:center;text-align:center;word-break:break-word;padding:15px 8px;border-radius:12px;background:#071321;border:1px dashed #456083;font-size:25px;font-weight:800;letter-spacing:.5px}.gapmark{color:#ffd15a}.toast{text-align:center;color:#78f4b7;font-size:12px;min-height:18px;margin-top:8px}.note{color:#9db2ce;font-size:12px;line-height:1.55;margin-top:10px}
</style>
</head>
<body><main class="wrap">
<div class="brand">SPY NAME STUDIO</div><div class="sub">FREE FIRE NAME GENERATOR</div>
<section class="panel">
 <div class="tabs">
  <button class="tab active" data-cat="Freestyle">Freestyle</button>
  <button class="tab" data-cat="Rusher">Rusher</button>
  <button class="tab" data-cat="Dragstar">Dragstar</button>
  <button class="tab" data-cat="Normal">Normal</button>
  <button class="tab" data-cat="Personal">Personal</button>
 </div>
 <label for="userName">নিজের নাম লিখুন</label>
 <input id="userName" type="text" maxlength="18" placeholder="যেমন: Rakib">
 <div class="actions"><button class="btn" id="next">NEXT</button><button class="btn alt" id="auto">AUTO NAME</button></div>
 <div class="switchrow"><span>Invisible Space <b id="switchText">ON</b></span><label class="switch"><input id="space" type="checkbox" checked><span class="slider"></span></label></div>
</section>
<section class="panel">
 <div class="small">নামের Preview · (· চিহ্নটি শুধু ফাঁকা জায়গা বোঝায়)</div>
 <div class="result" id="preview">メZᴇiRᴏN <span class="gapmark">·</span> ᴢ</div>
 <div class="actions"><button class="btn copy" id="copy">COPY NAME</button><button class="btn alt" id="another">ANOTHER</button></div>
 <div class="toast" id="toast"></div>
 <div class="note">কপি করা নামের মধ্যে Preview-এর · চিহ্ন থাকবে না; সেখানে Invisible Space থাকবে। Free Fire কিছু বিশেষ চিহ্ন গ্রহণ নাও করতে পারে।</div>
</section>
</main>
<script>
const data={
 Freestyle:[
 "ZeiRon","RaVix","BeNex","BoNex","ZiGZaG","VeXon","ZoNix","JaYro","KyZen","NeXor","VyRex","ZaVio","JeXon","RyZer","KaZix","XeNox","RoVik","ZeKro","MiRax","VaZon",
 "ReNix","JoVex","KyRox","ZaYen","NeVix","RaZon","XeRik","VoNex","ZeVox","KaYro","RyNex","BoRix","VaRox","JeZon","ZiVex","NoRix","KeZar","TyVox","ZaRix","VeKro",
 "RoZen","NyVex","JaRox","ZeNir","KaVex","ReZon","VyNox","BoZen","XeVik","RaKox","ZiRex","NoVex","KyRin","VaJex","ZeRax","JoNix","RyVox","NeZar","TaVex","KoRix",
 "ZaNox","VeRin","MiZex","RoVex","JaNir","KyVox","BeRix","ZeYro","NoZix","RaVox","VyZen","KaNex","JoRix","XeZon","NiVex","TyRox","ZaKro","ReVix","BoNix","ZeKix",
 "VaNir","RyZox","KeVox","JaVex","NoRax","ZiNex","RoKix","NeYro","KaZon","VyRix","BeZon","TaNex","JoZen","XeRox","RaYen","ZeVik","MiNox","KyZar","VaRix","BoVex",
 "ZaRin","ReXon","TyNix","NoZen","KaRox","JeVik","RyNox","ZiYen","VoRix","NeKro","ZeNox","RaZen","VaXen","KoVex","MiRox","JaZix","BeNox","KyVex","RoNix","TaZor",
 "XeNir","VyKro","JoVox","ZaMik","ReKix","BoYen","NiRox","ZeJex","KaVik","RyZon","NoKex","VaZen","JaNox","MiVex","TyZon","KoRax","BeVox","ZiKro","RoYen","NeRix",
 "ZaVex","KyNox","JeRix","VoZen","RaKix","XeYro","NoVik","TaRox","MiZon","ZeRox","VaKro","JoNex","RyVik","BeZix","KaYen","NiZor","VyRax","RoJex","KoNix","JaVox",
 "ZeMik","RaNox","TyVex","NeZix","BoRax","KyYen","VaRok","JoKix","XeVox","MiRex","ZaJin","ReVox","NoYen","KaZix","RyKro","BeNir","ZiVox","RoZar","TaVik","JeNox",
 "VoRax","NiVox","ZeKro","RaJex","KyRin","MiNex","ZaYor","JoRax","VeNix","BoKix","XeZar","NeVox","TyKro","KaRin","RyJex","ZiNox","VaRex","ReYen","NoZar","JaKix",
 "ZeVyn","RaMik","KyNir","BoVyn","NeJex","TaNox","VoKix","MiRyn","ZaRex","JoYen","XeKro","VyJin","BeRox","NoVyn","KaJex","RyNir","ZiRox","VaYen","ReKro","JaVyn",
 "KoZix","ZeRyn","RaVyn","TyJex","MiKro","NeRax","BoJin","KyRex","ZaNir","VoJex","XeRyn","JoZar","BeKro","NoJex","VaNox","ReZix","ZiVyn","KaRex","RyYen","TaVox",
 "JeKro","RoNex","NiJex","ZeYen","VyRox","KoVyn","MaRix","SaVex","FaRox","NaZix","LiVox","TeRyn","DaNex","PaVik","SuRox","HaZon","MoVex","LaRix","DiNox","PeZar"
 ],
 Rusher:["RaGon","HeLix","RuShX","DaRex","VaNox","KrYpT","ReAper","ZeRox","TaRix","NoVax","RyDer","KaRma","RaZer","ViPer","KoBra","XeNox","BlAze","DrAke"],
 Dragstar:["DrAxo","SkYro","BlAze","NiTro","XeRox","FlAme","VyPer","StOrM","RaZor","ThUnD","KyRex","JoLtX","SpArK","ReVox","ZaPex"],
 Normal:["Rakib","Sayem","Nirob","Tanim","Fahim","Nabil","Aryan","Sakib","Rifat","Mahin","Riyad","Siam","Rohan","Nayeem"]
};
const prefixes=["メ","亗","〆","乂","ツ","彡","々","么","・","★","✦","꧁"];
const suffixes=["ᴢ","ᴠ","ツ","亗","メ","ᴳ","x","ᴿ","ϟ","么","ᴋ","ᴘ","ᵛ","ᵡ","★","〆"];
const normalPre=["•","×","_","★","."],normalPost=["ツ","x","ᴢ","•","★","_"];
let category="Freestyle",index=0,current="";
const $=id=>document.getElementById(id);
function stylizePersonal(s){
 let out="",upper=true;
 for(const ch of s){if(/[a-z]/i.test(ch)){out+=upper?ch.toUpperCase():ch.toLowerCase();upper=!upper}else out+=ch;}
 return out;
}
function pick(a){return a[Math.floor(Math.random()*a.length)]}
function render(){
 let main="",pre="",post="";
 if(category==="Personal"){
  const raw=$("userName").value.trim();
  if(!raw){$("toast").textContent="আগে নিজের নাম লিখুন।";return;}
  main=stylizePersonal(raw);pre=pick(prefixes);post=pick(suffixes);
 }else if(category==="Normal"){
  const raw=$("userName").value.trim();
  main=raw?raw:pick(data.Normal);pre=pick(normalPre);post=pick(normalPost);
 }else{
  const arr=data[category];main=arr[index%arr.length];index++;
  // Alternate upper/lower case while keeping the Free Fire gamer-name look.
  main=stylizePersonal(main);
  pre=pick(prefixes);post=pick(suffixes);
 }
 const gap=$("space").checked?"ㅤ":"";
 current=pre+main+gap+post;
 $("preview").innerHTML=esc(pre+main)+(gap?' <span class="gapmark">·</span> ':' ')+esc(post);
 $("toast").textContent="";
 $("switchText").textContent=$("space").checked?"ON":"OFF";
}
function esc(s){return s.replace(/[&<>"']/g,c=>({"&":"&amp;","<":"&lt;",">":"&gt;",'"':"&quot;","'":"&#39;"}[c]))}
document.querySelectorAll(".tab").forEach(b=>b.onclick=()=>{
 document.querySelectorAll(".tab").forEach(x=>x.classList.remove("active"));
 b.classList.add("active");category=b.dataset.cat;index=0;render();
});
$("next").onclick=render;$("another").onclick=render;
$("auto").onclick=()=>{if(category==="Personal"){$("userName").value="";category="Freestyle";document.querySelectorAll(".tab").forEach(x=>x.classList.toggle("active",x.dataset.cat===category));}render()};
$("space").onchange=render;
$("copy").onclick=async()=>{try{await navigator.clipboard.writeText(current);$("toast").textContent="নাম কপি হয়েছে! Free Fire-এ Paste করুন।"}catch(e){$("toast").textContent="কপি হয়নি—ফোনের ব্রাউজারে Clipboard অনুমতি দিন।"}};
render();
</script>
</body></html># MD-Raki