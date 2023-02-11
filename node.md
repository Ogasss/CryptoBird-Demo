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
