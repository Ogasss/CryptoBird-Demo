## svg使用方式
```
    <template>
        <div>
            <img :src="logo"/>
        </div>
    </template>

    <script>
    import logo from '../assets/icons/logo.svg'
    export default {
        setup(){
            return{
                logo
            }
        }
    }
    </script>
```
/* CryptoBird */

width: 108px;
height: 26px;

font-family: 'Aeonik';
font-style: normal;
font-weight: 500;
font-size: 22px;
line-height: 26px;

color: #FFFFFF;


/* Inside auto layout */
flex: none;
order: 0;
flex-grow: 0;
