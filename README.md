- 👋 Hi, I’m @Lecsonrc
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!--
Lecsonrc/Lecsonrc is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
-
Observando mais e falando menos !
Revoluicionar o mundo digital
tenho ideias genias  para o mundo moderno...
Avaliando nova tecnologia.
direct!
<time> 
    
const { ethers } = require("ethers");

// 1. Conexão com a rede
const provider = new ethers.JsonRpcProvider("SUA_URL_DO_ALCHEMY");
const wallet = new ethers.Wallet("SUA_CHAVE_PRIVADA", provider);

// 2. Endereço do Roteador da DEX (Ex: PancakeSwap ou Uniswap)
const routerAddress = "0x..."; 
const routerAbi = [...]; // ABI das funções de swap

const dexRouter = new ethers.Contract(routerAddress, routerAbi, wallet);

// 3. Função de Swap
async function buyToken(tokenIn, tokenOut, amountIn) {
    const tx = await dexRouter.swapExactTokensForTokens(
        amountIn,
        0, // Slippage (ajustar para segurança!)
        [tokenIn, tokenOut],
        wallet.address,
        Math.floor(Date.now() / 1000) + 60 * 10 // Deadline
    );
    console.log("Transação enviada:", tx.hash);
}
