<script>
    let expensesList = [];
    let expenseName = ""
    let expenseSum = "";

    function addExpense() {        
        if(expenseName !== "" && expenseSum !== "" && expenseSum != null) {
            expensesList = [
                ...expensesList,
                {
                    name: expenseName,
                    sum: expenseSum                    
                }
            ];

            expenseName = "";
            expenseSum = "";
        }
    }

    function removeExpense(index) {
        expensesList.splice(index, 1);
        expensesList = expensesList;
    }
</script>

<main>
    <h1>Учёт расходов</h1>

    <div class="form_and_button">
        <form on:submit|preventDefault={addExpense}>
            <div>
                <p><strong>Название:</strong></p>
                <input bind:value={expenseName}/>
            </div>
            <div>
                <p><strong>Сумма:</strong></p>
                <input bind:value={expenseSum} type='number'/>
            </div>
        </form>
        <button class="add_expense" on:click={addExpense}>Добавить</button>        
    </div>
    
    <div class="expenses">
        <table>
            <tr><th>Название</th><th>Сумма</th><th>Действия</th></tr>
            {#each expensesList as expense, index}             
                <tr>
                    <th>{ expense.name }</th>
                    <th>{ expense.sum }</th>
                    <th><button class="delete_expense" on:click={() => removeExpense(index)}>Удалить</button></th>
                </tr>                
            {/each}
        </table>
    </div>
</main>

<style>
    main {
        display: flex;
        flex-direction: column;
        margin: 100px auto;
        min-height: 100%;
        max-width: 70%;
        min-width: auto;
        padding: 5vmin;
        box-sizing: border-box;
        background: white;
        border-radius: 40px;
        box-shadow: 0 14px 28px rgba(0,0,0,0.25), 0 10px 10px rgba(0,0,0,0.22);
    }

    h1 {
        text-align: center;
    }

    form {
        width: fit-content;
        max-width: 500px;
        display: block;
        margin-bottom: 1rem;        
    }

    form p {
        font-size: 20px;     
    }
    
    .form_and_button {
        position: relative;
        display: flex;
        flex-direction:row;
    }

    input {
        display: block;
        min-width: 250px;
        min-height: 25px;
    }

    .add_expense {
        width: 200px;
        height: 40px;
        background-color: green;
        color: white;
        border-radius: 35px;
        border-color: black;
        border-width: 4px;
        font-size: 14px;
    }    

    .add_expense:hover {
        background-color: rgb(3, 177, 58)    
    }

    .add_expense {
        position: absolute;
        bottom: 15px;
        right: 0;
    }

    table {
        min-width: 100%;
        border-radius: 25px;
        border-color: rgba(128, 128, 128, 0.655);
        border-width: 2px;
        border-style: solid; 
        border-collapse: collapse;       
    }

    th {        
        text-align: left;
        padding: 10px;
        border-radius: 5px;
        border-color: rgba(128, 128, 128, 0.655);
        border-width: 2px;
        border-style: solid; 
    }

    .delete_expense {
        width: 150px;
        height: 40px;
        background-color: rgb(154, 15, 0);
        color: white;
        border-width: 0;
        border-radius: 15px;
        font-size: 14px;
    }

    .delete_expense:hover {
        background-color: rgb(204, 20, 0);
    }
</style>