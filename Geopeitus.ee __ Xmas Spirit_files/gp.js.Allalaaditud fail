$(document).ready(function() {

$("#events a,.gphelp,.tt").tooltip({
    track: true,
    delay: 0,
    showURL: false,
    showBody: " :: ",
    fade: 250
});

$("#tagadd-button").click(function () {
  $("#tagadd").toggle();
  this.blur();
  return false;
});

$("#mynote").autoResizable().keydown();

/*
$("a[rel^='lightbox']").fancybox({ 'hideOnContentClick': true }); 

$("a.iframe").fancybox({ 'zoomSpeedIn': 300, 'zoomSpeedOut': 0, 'frameHeight': 200 }); 

$("a.ajaxlb").fancybox({ 'overlayShow': false, 'hideOnContentClick': false, centerOnScroll: false }); 
*/

$("input.focus:last").focus();

});

function CheckTB(gccwp)
{
    $("#gcctb").html('<img src="/ug/progress.gif"> Kontrollin ...').load("/?p=4501&wp="+gccwp);
}

function TagSave (ref_type, ref_id)
{
    var tagname = $('#newtag').val();
    $("#mytags").html('<img src="/ug/progress.gif"> Salvestan ...').load("/index.php", { p: "4502", a: 'savetag', t: ref_type, r: ref_id, n: tagname });
    $('#newtag').val('');
    $("#tagadd").hide();
}

function TagDelete (id, ref_type, ref_id)
{
    $("#mytags").load("/index.php", { p: "4502", a: 'deletetag', i: id, t: ref_type, r: ref_id });
}

function TagCopy (ref_type, ref_id, tag)
{
    $("#mytags").load("/index.php", { p: "4502", a: 'savetag', t: ref_type, r: ref_id, n: tag });
}

function IgnoreCache(c)
{
    $("#cIgn").html('<img border="0" alt="" class="icon16" src="/ug/icons/table_delete.png"> <img src="/ug/progress.gif"> salvestan ...').load("/?p=4504&c="+c);
}

function DontIgnoreCache(c)
{
    $("#cIgn").html('<img border="0" alt="" class="icon16" src="/ug/icons/table_add.png"> <img src="/ug/progress.gif"> salvestan ...').load("/?p=4504&d=1&c="+c);
}

function MynoteAdd ()
{
    $("#mynote-add").fadeOut('normal', function() {
        $("#mynote-save").fadeIn('normal');
    });
    $("#mynote-wrap").slideDown('normal');
    $("#mynote").focus();
}

function MynoteSave (c)
{
  var note = $('#mynote').val();
  $("#mynote-status").html('<img src="/ug/progress.gif"> Salvestan ...').fadeIn('fast').load("/index.php", { p: "4505", a: 'save', c: c, n: note });
  setTimeout(function() {$("#mynote-status").fadeOut('slow')} , 1500);
}

function MyPicDelete (f)
{
    if (confirm("Kas sa soovid foto kustutada?")) {
	$.post("/index.php", { p: "4506", f: f }, function(data) {
	    if (data == 'ok') {$('#pic'+f).fadeOut()}
	});
    }
}

function ThumbSave (ref_type, ref_id)
{
    $("#e-"+ref_id).html('<img src="/ug/progress.gif">').load("/index.php", { p: "4513", a: 's', e: ref_id }, function() { ActivateTooltips();});
}

function ThumbDelete (ref_type, ref_id)
{
    $("#e-"+ref_id).html('<img src="/ug/progress.gif">').load("/index.php", { p: "4513", a: 'd', e: ref_id }, function() { ActivateTooltips();});
        ActivateTooltips();
}


function ActivateTooltips () {
        $(".thumbcount").tooltip({ 
                showURL: false,
            bodyHandler: function() { 
                        var ref_id = $(this).data("refid")
                var result = $("<span/>").html("<img src='/ug/progress.gif'>"); 
                    $.get("/index.php", { p: "4514", e: ref_id }, function(data) { result.html(data); }, "html"); 
                return result; 
                } 
        });
}



/*
 * jQuery autoResize (textarea auto-resizer)
 * @copyright James Padolsey http://james.padolsey.com
 * @version 1.04
 */
/*
(function(a){a.fn.autoResize=function(j){var b=a.extend({onResize:function(){},animate:true,animateDuration:150,animateCallback:function(){},extraSpace:20,limit:1000},j);this.filter('textarea').each(function(){var c=a(this).css({resize:'none','overflow-y':'hidden'}),k=c.height(),f=(function(){var l=['height','width','lineHeight','textDecoration','letterSpacing'],h={};a.each(l,function(d,e){h[e]=c.css(e)});return c.clone().removeAttr('id').removeAttr('name').css({position:'absolute',top:0,left:-9999}).css(h).attr('tabIndex','-1').insertBefore(c)})(),i=null,g=function(){f.height(0).val(a(this).val()).scrollTop(10000);var d=Math.max(f.scrollTop(),k)+b.extraSpace,e=a(this).add(f);if(i===d){return}i=d;if(d>=b.limit){a(this).css('overflow-y','');return}b.onResize.call(this);b.animate&&c.css('display')==='block'?e.stop().animate({height:d},b.animateDuration,b.animateCallback):e.height(d)};c.unbind('.dynSiz').bind('keyup.dynSiz',g).bind('keydown.dynSiz',g).bind('change.dynSiz',g)});return this}})(jQuery);
*/
/*
 * jQuery Animated Auto-Resizable Textarea Plugin v1.0
 *
 * Copyright (c) 2009 - 2010 Wayne Haffenden
 * http://www.waynehaffenden.com/Blog/jQuery-AutoResizable-Plugin
 *
 * $Id: jquery.autoResizable.js, v 1.0 2009-12-30 01:53:14Z whaffenden $
 *
 * Dual licensed under the MIT and GPL licenses:
 *   http://www.opensource.org/licenses/mit-license.php
 *   http://www.gnu.org/licenses/gpl.html
 */
;(function(e){e.fn.autoResizable=function(o){var c=e.extend({animate:true,animateDuration:200,maxHeight:500,onBeforeResize:null,onAfterResize:null,padding:20,paste:true,pasteInterval:100},o);return this.filter("textarea").each(function(){var a=e(this),j=a.height(),f=0,g=null,p=c.animate,q=c.animateDuration,h=c.maxHeight,l=c.onBeforeResize,i=c.onAfterResize,r=c.padding,s=c.paste,t=c.pasteInterval,n=function(){var b={};e.each(["height","letterSpacing","lineHeight","textDecoration","width"],function(k,m){b[m]=a.css(m)});return a.clone().removeAttr("id").removeAttr("name").css({left:-99999,position:"absolute",top:-99999}).css(b).attr("tabIndex",-1).insertBefore(a)}(),d=function(){if(j<=0)j=a.height();n.height(0).val(a.val()).scrollTop(1E4);var b=Math.max(n.scrollTop()+r,j);if(!(b===f||b>=h&&f===h)){if(b>=h){b=h;a.css("overflow-y","auto")}else a.css({overflow:"hidden",overflowY:"hidden"});var k=true;if(l!==null)k=l.call(a,f,b);f=b;if(k!==false)if(p&&a.css("display")==="block")a.stop().animate({height:b},q,function(){i!==null&&i.call(a)});else{a.height(b);i!==null&&i.call(a)}}};a.css({overflow:"hidden",resize:"none"});a.unbind(".autoResizable").bind("keydown.autoResizable",d).bind("keyup.autoResizable",d).bind("change.autoResizable",d).bind("focus.autoResizable",function(){if(s)g=setInterval(d,t);d()}).bind("blur.autoResizable",function(){if(g!==null){clearInterval(g);g=null}})})}})(jQuery);
