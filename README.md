<img src='fortran.png'/>

## An  elegant way to embed fortran code inside html

Just upload the two files <b>comis.cgi</b> and <b>main.cgi</b> to your linux server and start writing your Fortran 77 code (free source format) inside HTML.
See <i>index.html</i> for details and read <i>comis.ps</i> (p4-9) for some minor limitations.
#### Example 1
<pre>
&lt;div id="div-1">&lt;div> &lt;-- HERE THE RESULT COMES OUT -->
&lt;template id='fortran-1'> &lt;!-- AND HERE IS THE FORTRAN CODE (No need to include SUBROUTINE and END commands)-->
do i = 1, 100
if(mod(i,2) == 0) print*, i
enddo
&lt;template>
</pre>

Result 1

2 4 6 8 10 12 14 16 18 20 22 24 26 28 30 32 34 36 38 40 42 44 46 48 50 52 54 56 58 60 62 64 66 68 70 72 74 76 78 80 82 84 86 88 90 92 94 96 98 100 

#### You can also use the <a href='https://www.dislin.de/' target='_blank'>DISLIN</a> ploting library !!!

#### Example 2
<pre>
&lt;div id="div-1">&lt;div>
&lt;template id='fortran-1'>
do i = 1, 100 if(mod(i,2) == 0) print*, i enddo &lt;!-- YES IN ONE LINE !! -->
&lt;template>

&lt;div id="div-2">&lt;div> &lt;!-- CHANGE DIV (AND TEMPLATE) NUMBER IF THERE ARE MANY SUBROUTINES IN THE SAME .html FILE -->
&lt;template id='fortran-2'>
call metafl('virt') call scrmod ('revers')
call disini
call unit (0)

do i = 1, 1000
  call setrgb (rnd(), rnd(), rnd())
  call circle (int(rnd()*2970), int(rnd()*2100), int(rnd()*200))
enddo

call rpng ('img.png') call disfin
print*, '&lt;img src="img.png"/>' &lt;-- YES you can also use HTML inside FORTRAN !!!
</pre>

Result 2

2 4 6 8 10 12 14 16 18 20 22 24 26 28 30 32 34 36 38 40 42 44 46 48 50 52 54 56 58 60 62 64 66 68 70 72 74 76 78 80 82 84 86 88 90 92 94 96 98 100 

<img src='img.png' width="500"/>

#### Work based on <a href='https://cernlib.web.cern.ch/version.html' target='_blank'>CERNLIB</a>.
