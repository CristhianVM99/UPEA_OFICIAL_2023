<template>
    <ul class="mainmenu">
        <li class="has-droupdown"><n-link to="/">Inicio</n-link>
            <ul class="submenu">
                <li><n-link to="/about-us-two">Sobre Nosotros</n-link></li>
                <li><n-link to="/contact-me">Contacto</n-link></li>                
            </ul>
        </li>
        <!--<li class="has-droupdown"><n-link to="">Areas y Carreras</n-link>            
            <ul class="mega-menu">                               
                <li v-for="(area, id_area) in menuAreasyCarreras" :key="id_area">
                    <h6 style="font-size: 0.7em;" class="menu-title">{{ area.area }}</h6>
                    <ul class="submenu">
                        <li v-for="(carrera, id_carrera) in area.carreras" :key="id_carrera">
                            <a style="font-size: 0.7em;" :href="getLinkCarrera(carrera.nombre_simple)" target="_blank">{{ carrera.carrera }}</a>
                        </li>                        
                    </ul>
                </li>
            </ul>          
        </li>-->

        <li class="has-droupdown"><n-link to="">Unidades Administrativas</n-link>
            <ul class="submenu">
                <li><a href="https://vicerrectorado.upea.bo/l">vicerectorado</a></li>
                <li><a href="https://www.sie.upea.bo/l">unidad de sistemas de informacion y estadistica</a></li>
                <li><a href="https://registrosadmisiones.upea.bo/">registros y admiciones</a></li>
            </ul>                    
        </li>

        <li class="has-droupdown"><n-link to="">Avisos</n-link>
            <ul class="submenu">
                <li><n-link to="/convocatorias/publicaciones">publicaciones</n-link></li>
                <li><n-link to="/convocatorias/servicios">servicios</n-link></li>                
                <li><n-link to="/convocatorias/gacetas">gacetas</n-link></li>
                <li><n-link to="/convocatorias/auditorias">auditorias</n-link></li>
                <li><n-link to="/convocatorias/eventos">eventos</n-link></li>
                <li><n-link to="/convocatorias/videos">videos</n-link></li>                                
            </ul>
        </li>
        <li class="has-droupdown"><n-link to="">Mas</n-link>
            <ul class="submenu">
                <li><a href="http://repositorio.upea.bo/" target="_blank">repositorio institucional</a></li>
                <li><a href="https://disbedc.upea.bo/" target="_blank">disbec</a></li>
                <li><a href="http://mibiblioteca.upea.bo/" target="_blank">mi biblioteca upea</a></li>
                <li><a href="https://fm100.upea.bo/" target="_blank">radio upea</a></li>
                <li><a href="https://tv.upea.bo/" target="_blank">tv upea</a></li>
            </ul>
        </li>
    </ul>
</template>
<script>
    import { useInstitucionStore } from '@/stores/store'
    export default{
        data() {
            return {
                menuAreasyCarreras: useInstitucionStore().menuAreasyCarreras,
                linksCarreras: useInstitucionStore().linksCarreras,
            }
        },
        methods: {
            getLinkCarrera(links){
                let link = ""
                this.linksCarreras.forEach(element =>{        
                    if(element.carrera == links){
                        link = element.link
                    }
                })
                return link
            }
        },
    }
</script>