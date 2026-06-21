# 11424144-Finaltern
$$\text{1. 基礎參數與週期分析}$$

$$\text{單缸四衝程柴油機的曲軸每轉兩圈（} 720^\circ \text{ 或 } 4\pi \text{ rad）完成一個工作循環。因此，激勵力的運作週期與頻率如下：}$$

$$\text{曲軸轉速：} n = 1500 \text{ rpm}$$
$$\text{曲軸旋轉角速度：} \omega_r = \frac{2\pi n}{60} = \frac{2\pi \times 1500}{60} = 50\pi \text{ rad/s}$$
$$\text{曲軸旋轉頻率（基頻）：} f_r = \frac{n}{60} = \frac{1500}{60} = 25 \text{ Hz}$$
$$\text{燃氣爆發力週期：} T = \frac{4\pi}{\omega_r} = \frac{4\pi}{50\pi} = 0.08 \text{ s}$$
$$\text{爆發力基波角頻率（工作循環頻率）：} \omega_0 = \frac{2\pi}{T} = \frac{\omega_r}{2} = 25\pi \text{ rad/s}$$
$$\text{爆發力基波頻率：} f_0 = \frac{1}{T} = 12.5 \text{ Hz}$$

---

$$\text{2. 激勵力的傅里葉級數展開}$$

$$\text{由於爆發力 } F(\varphi) \text{ 是以 } T \text{ （對應曲軸轉角 } 4\pi \text{）為週期的函數，其數學分段表達式為：}$$
$$ F(\varphi) = 
\begin{cases} 
F_{\max} \left(1 - \frac{\varphi}{\pi}\right), & 0 \le \varphi \le \pi \\
0, & \pi < \varphi \le 4\pi
\end{cases} $$

$$\text{將其展開為傅里葉級數形式：}$$
$$F(\varphi) = a_0 + \sum_{k=1}^{\infty} \left( a_k \cos\left(k \cdot \frac{\varphi}{2}\right) + b_k \sin\left(k \cdot \frac{\varphi}{2}\right) \right)$$

$$\text{直流分量（平均力）} a_0 \text{：}$$
$$a_0 = \frac{1}{4\pi} \int_{0}^{4\pi} F(\varphi) d\varphi = \frac{1}{4\pi} \int_{0}^{\pi} F_{\max} \left(1 - \frac{\varphi}{\pi}\right) d\varphi$$
$$a_0 = \frac{F_{\max}}{4\pi} \left[ \varphi - \frac{\varphi^2}{2\pi} \right]_0^\pi = \frac{F_{\max}}{4\pi} \left( \pi - \frac{\pi}{2} \right) = \frac{F_{\max}}{8}$$
$$\text{代入 } F_{\max} = 15 \text{ kN：}$$
$$a_0 = \frac{15}{8} = 1.875 \text{ kN}$$

$$\text{餘弦項係數 } a_k \text{：}$$
$$a_k = \frac{2}{4\pi} \int_{0}^{\pi} F_{\max} \left(1 - \frac{\varphi}{\pi}\right) \cos\left(\frac{k\varphi}{2}\right) d\varphi$$
$$a_k = \frac{4 F_{\max}}{\pi^2 k^2} \left[ 1 - \cos\left(\frac{k\pi}{2}\right) \right]$$

$$\text{正弦項係數 } b_k \text{：}$$
$$b_k = \frac{2}{4\pi} \int_{0}^{\pi} F_{\max} \left(1 - \frac{\varphi}{\pi}\right) \sin\left(\frac{k\varphi}{2}\right) d\varphi$$
$$b_k = \frac{F_{\max}}{\pi^2 k^2} \left[ 2k\pi - 4\sin\left(\frac{k\pi}{2}\right) \right]$$

---

$$\text{3. 振動頻率成分分析}$$

$$\text{第 } k \text{ 階諧波對應的振動頻率 } f_k \text{ 為：}$$
$$f_k = k \cdot f_0 = k \cdot 12.5 \text{ Hz} \quad (k = 1, 2, 3, \dots)$$

$$\text{各階次頻率分布如下：}$$
$$\text{k=1 (0.5 階次): } f_1 = 12.5 \text{ Hz}$$
$$\text{k=2 (1.0 階次): } f_2 = 25.0 \text{ Hz}$$
$$\text{k=3 (1.5 階次): } f_3 = 37.5 \text{ Hz}$$
$$\text{k=4 (2.0 階次): } f_4 = 50.0 \text{ Hz}$$
$$\text{k=9 (4.5 階次): } f_9 = 112.5 \text{ Hz}$$
$$\text{k=10 (5.0 階次): } f_{10} = 125.0 \text{ Hz}$$

---

$$\text{4. 共振判斷結論}$$

$$\text{已知柴油機機體的一階固有頻率為：} f_n = 120 \text{ Hz}$$
$$\text{計算固有頻率與基頻的比值：} \frac{f_n}{f_0} = \frac{120}{12.5} = 9.6$$

$$\text{結論分析：}$$
$$\text{1. 因為 } 120 \text{ Hz 介於第 9 階（} 112.5 \text{ Hz）與第 10 階（} 125 \text{ Hz）之間，故不會發生精確共振。}$$
$$\text{2. 但第 10 階諧波與固有頻率差距僅 } \left| \frac{125 - 120}{120} \right| \times 100\% = 4.17\% \text{，在低阻尼下仍有強迫振動放大風險。}$$
