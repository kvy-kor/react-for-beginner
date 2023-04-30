노마드코더 : https://nomadcoders.co/
바벨 : https://babeljs.io/

* 클릭하면 몇 번 했는지 변환해주는 프로그램
<!DOCTYPE html>
<html>
    <body>
        <div id="root"></div>
    </body>
    <script crossorigin src="https://unpkg.com/react@18/umd/react.production.min.js"></script>
    <script crossorigin src="https://unpkg.com/react-dom@18/umd/react-dom.production.min.js"></script>
    <script crossorigin src ="https://unpkg.com/@babel/standalone/babel.min.js"></>

    <script type = "text/babel">
        function App () {
            const [counter, setCounter] = React.useState(0);
            const onClick = () => {
                //setCounter(counter + 1);
                setCounter((current)=>current + 1);
            };
            return (
                <div>
                    <h3>Total clicks : {counter}</h3>
                    <button onClick={onClick} >Click me</button>
                </div>
            );
        }
        const root = document.getElementById("root");
        ReactDOM.render(<App />, root);
    </script>
</html>

* Super Converter : 단위 변환 프로그램
<!DOCTYPE html>
<html>
    <body>
        <div id="root"></div>
    </body>
    <script crossorigin src="https://unpkg.com/react@18/umd/react.production.min.js"></script>
    <script crossorigin src="https://unpkg.com/react-dom@18/umd/react-dom.production.min.js"></script>
    <script crossorigin src ="https://unpkg.com/@babel/standalone/babel.min.js"></script>

    <script type = "text/babel">
        function App () {
            const [minutes, setMinutes] = React.useState(0);
            const onChange = (event) => {
                setMinutes(event.target.value);
            };
            const reset = () => setMinutes(0);
            return (
                <div>
                    <h1>Super Converter</h1>
                    <div>
                        <label for="minutes">Minutes</label>
                        <input 
                            value = {minutes}
                            id = "minutes" 
                            placeholder = "Minutes" 
                            type = "number"
                            onChange={onChange}
                        />
                    </div>
                    <div>
                        <label for="hours">Hours</label>
                        <input 
                            value = {Math.round(minutes / 60)}
                            id = "hours" 
                            placeholder = "Hours" 
                            type = "number"
                            disabled
                        />
                    </div>
                    <button onClick = {reset}>Reset</button>
                </div>
            );
        }
        const root = document.getElementById("root");
        ReactDOM.render(<App />, root);
    </script>
</html>