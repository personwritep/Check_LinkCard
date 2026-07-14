// ==UserScript==
// @name        Check LinkCard
// @namespace    http://tampermonkey.net/
// @version        0.3
// @description        ブログ記事上のリンクカードの修復チェックツール
// @author        Ameba Blog User
// @match        https://ameblo.jp/*
// @noframes
// @icon         https://www.google.com/s2/favicons?sz=64&domain=ameblo.jp
// @grant        none
// @updateURL        https://github.com/personwritep/Check_LinkCard/raw/main/Check_LinkCard.user.js
// @downloadURL        https://github.com/personwritep/Check_LinkCard/raw/main/Check_LinkCard.user.js
// ==/UserScript==



let target=document.querySelector('head > title');
let monitor=new MutationObserver(main);
monitor.observe(target, { childList: true });

main();


function main(){

    let disp=
        '<div class="rapid">◀◀</div>'+
        '<div class="date_disp"></div>'+
        '<div class="card_disp">'+
        '<div class="info"></div>'+
        '<div class="clamp"></div>'+
        '<div class="m_height"></div>'+
        '<div class="l_height"></div>'+
        '<style>'+
        '.card_disp { position: fixed; top: calc(50% - 54px); left: 10px; z-index: 200; '+
        'font: 16px/22px Meiryo; color: #000; background: #fff; min-width: 132px; '+
        'border: 1px solid #009688; box-shadow: 2px 2px 6px 0 #66666650; }'+
        '.info { text-align: center; } '+
        '.c_count { padding: 5px 10px 2px; color: #fff; background: #000; } '+
        '.c_count_0 { padding: 5px 10px 2px; color: #fff; background: #bbb; } '+
        '.c_order { padding: 5px 10px 2px; margin-bottom: 6px; '+
        'color: #fff; background: #009caa; } '+
        '.clamp, .m_height, .l_height { padding: 0 0 0 12px; } '+
        '.info:has(.c_order) ~ .l_height { margin-bottom: 6px; } '+
        '.ex_card { color: #2196f3; text-shadow: 0 0 1px #2196f3; } '+

        '.rapid { position: absolute; top: calc(50% - 136px); left: 11px; z-index: 200; '+
        'font: 16px/22px Meiryo; color: #333; background: #fff; border: 1px solid #444; '+
        'border-radius: 3px; padding: 2px 6px 0; box-shadow: 2px 2px 6px 0 #66666650; '+
        'display: none; } '+

        '.date_disp { position: absolute; top: calc(50% - 100px); left: 10px; z-index: 200; '+
        'font: 19px/20px Meiryo; color: #333; background: #fff; width: 132px; height: 18px; '+
        'padding: 6px 0; text-align: center; '+
        'border: 1px solid #444; box-shadow: 2px 2px 6px 0 #66666650; } '+

        'html { scroll-behavior: unset !important; }'+
        '</style><div>';

    if(!document.querySelector('.card_disp ')){
        document.body.insertAdjacentHTML('beforeend', disp); }


    let retry=0;
    let interval=setInterval(wait_target, 200);
    function wait_target(){
        retry++;
        if(retry>10){
            clearInterval(interval); }
        let blog=document.querySelector('#entryBody');
        if(blog){
            clearInterval(interval);
            setTimeout(()=>{
                check_card(blog);
            }, 200); }}



    function check_card(blog){
        sessionStorage.setItem('CheckLinkCard', 0);
        let order;

        document.addEventListener('keydown', function(event){
            if(event.keyCode==32){
                event.preventDefault();
                event.stopImmediatePropagation();
                if(!event.ctrlKey){
                    order=sessionStorage.getItem('CheckLinkCard')/1;
                    sender(order); }}
            else if(event.ctrlKey){ //「Ctrl」キーで「カウント0」の自動ページ送りを「ON / OFF」
                if(sessionStorage.getItem('CheckLinkCard_run')!=0){ //「0:OFF」「1:ON」
                    sessionStorage.setItem('CheckLinkCard_run', 0); }
                else{
                    sessionStorage.setItem('CheckLinkCard_run', 1); }
                rapid_disp(); }
        });



        function sender(order){
            let card=blog.querySelectorAll('.ogpCard_link');
            if(order<card.length){
                let target_card=card[order];
                target_card.scrollIntoView({block: 'center'}); // 画面の中央に配置
                view_card(target_card, order);
                sessionStorage.setItem('CheckLinkCard', order+1); }
            else if(order==card.length){
                let card_disp=document.querySelector('.card_disp');
                if(card_disp){
                    card_disp.remove(); }

                let next=document.querySelector('.skin-pagingPrev, .pagingPrev, .previousPage');
                if(next){
                    let link=next.href;
                    if(link){
                        location.href=link; }}}

        } // sender()



        function view_card(target_card, order){
            let info=document.querySelector('.info');
            let clamp_p=document.querySelector('.clamp');
            let m_height_p=document.querySelector('.m_height');
            let l_height_p=document.querySelector('.l_height');

            if(info && clamp_p && m_height_p && l_height_p){
                info.innerHTML='<p class="c_order">'+ (order+1) +'</p>';

                let title=target_card.querySelector('.ogpCard_title');
                if(title){ // 標準・コンパクト・小型タイプのカード
                    let clamp=title.style.WebkitLineClamp;
                    clamp_p.innerHTML='<p>clamp: '+ clamp +'</p>';

                    let m_height=title.style.maxHeight;
                    if(m_height=='44px' || m_height=='22px'){ // 適正化済み
                        m_height_p.innerHTML='<p>max-h: '+ m_height +'</p>'; }
                    else{ // 未適正化
                        m_height_p.innerHTML=
                            '<p style="background: red">max-h: '+ m_height +'</p>'; }
                    let l_height=title.style.lineHeight;
                    if(l_height=='1.25'){ // 適正化済み
                        l_height_p.innerHTML='<p>line-h: '+ l_height +'</p>'; }
                    else{ // 未適正化
                        l_height_p.innerHTML='<p style="background: red">line-h: '+ l_height +'</p>'; }}
                else{
                    let title_s=target_card.querySelector('.ogpCard_link>span>span');
                    if(title_s){ // 軽量化タイプのカード
                        let clamp=title_s.style.WebkitLineClamp;
                        clamp_p.innerHTML='<p class="ex_card">clamp: '+ clamp +'</p>';

                        let m_height=title_s.style.maxHeight;
                        m_height_p.innerHTML='<p class="ex_card">max-h: '+ m_height +'</p>';

                        let l_height=title_s.style.lineHeight;
                        l_height_p.innerHTML='<p class="ex_card">line-h: '+ l_height +'</p>'; }}

            } //  if(clamp_p && m_height_p && l_height_p)

        } // view_card()



        rapid_disp();
        get_date();
        info_disp();



        function rapid_disp(){
            let rapid=document.querySelector('.rapid');
            if(rapid){
                if(sessionStorage.getItem('CheckLinkCard_run')==0){
                    rapid.style.display='none'; }
                else{
                    rapid.style.display='block'; }}}



        function get_date(){
            let app_id=document.querySelector('head script[type="application/ld+json"]');
            if(app_id){
                let data=app_id.textContent;
                let regex=/"datePublished"[^T]*/;
                let date=data.match(regex).toString();
                if(date){
                    date=date.replace('"datePublished":"', '');
                    let date_disp=document.querySelector('.date_disp');
                    if(date_disp){
                        date_disp.textContent=date; }}}}



        function info_disp(){
            let card=blog.querySelectorAll('.ogpCard_link');
            let info=document.querySelector('.info');
            if(card.length==0){
                if(info){
                    info.innerHTML='<p class="c_count_0">'+ card.length +'</p>'; }
                if(sessionStorage.getItem('CheckLinkCard_run')!=0){
                    setTimeout(()=>{
                        let next=document.querySelector('.skin-pagingPrev, .pagingPrev, .previousPage');
                        if(next){
                            let link=next.href;
                            if(link){
                                location.href=link; }}}, 400); }}
            else{
                if(info){
                    info.innerHTML='<p class="c_count">'+ card.length +'</p>'; }}

        } // info_disp()

    } // check_card()

} // main()
