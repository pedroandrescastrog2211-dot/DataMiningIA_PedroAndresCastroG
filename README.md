
# Data Mining con IA: Factores de Éxito en E-Commerce 🚀

## 1. Objetivo y Pregunta Central
¿Qué características del producto (Precio, Categoría, Descuento, Calificación de usuarios) determinan que se convierta en un éxito de ventas (60 o más unidades vendidas)?

## 2. Fuente de los Datos y Limpieza
* **Tamaño:** 300 registros (productos).
* **Proceso de Limpieza con IA:**
  * Homogeneización de texto en la variable `Categoria` (corrección de mayúsculas/minúsculas).
  * Imputación de precios erróneos (valores negativos de -99.0) utilizando la mediana por categoría.
  * Rellenado de valores nulos (`NaN`) en `Calificacion` con el promedio general.
  * Creación de la variable objetivo binaria `Exito_Ventas`.

---

<details>
<summary style="font-size: 1.2em; font-weight: bold; color: #2ea44f; cursor: pointer; padding: 10px; border: 2px solid #2ea44f; border-radius: 6px; background-color: #f6f8fa; display: inline-block;">
  📊 ▶ Haz clic aquí para desplegar el Dataset Completo (300 filas)
</summary>

<br>

| Registro | Categoría | Precio ($) | Descuento (%) | Calificación | Éxito de Ventas |
| :---: | :--- | :---: | :---: | :---: | :---: |
| **1** | Electrónica | 120.50 | 10 | 4.5 | Sí |
| **2** | Ropa | 45.00 | 5 | 3.8 | No |
| **3** | Hogar | 89.99 | 15 | 4.2 | Sí |
| **4** | Deportes | 25.00 | 0 | 4.0 | No |
| **5** | Electrónica | 210.00 | 20 | 4.8 | Sí |
| **6** | Juguetes | 15.50 | 10 | 3.5 | No |
| **7** | Ropa | 32.00 | 0 | 3.9 | No |
| **8** | Hogar | 115.00 | 25 | 4.6 | Sí |
| **9** | Deportes | 45.50 | 5 | 4.1 | No |
| **10** | Electrónica | 99.99 | 10 | 4.3 | Sí |
| **11** | Juguetes | 22.00 | 15 | 3.7 | No |
| **12** | Ropa | 18.50 | 5 | 3.6 | No |
| **13** | Hogar | 150.00 | 30 | 4.7 | Sí |
| **14** | Deportes | 60.00 | 10 | 4.2 | Sí |
| **15** | Electrónica | 135.00 | 15 | 4.4 | Sí |
| **16** | Juguetes | 29.99 | 0 | 3.8 | No |
| **17** | Ropa | 55.00 | 10 | 4.0 | No |
| **18** | Hogar | 75.00 | 12 | 4.1 | Sí |
| **19** | Deportes | 85.00 | 20 | 4.3 | Sí |
| **20** | Electrónica | 250.00 | 25 | 4.9 | Sí |
| **21** | Ropa | 41.20 | 10 | 4.0 | No |
| **22** | Hogar | 112.50 | 15 | 4.2 | Sí |
| **23** | Deportes | 29.90 | 5 | 3.9 | No |
| **24** | Juguetes | 18.00 | 0 | 3.6 | No |
| **25** | Electrónica | 185.00 | 20 | 4.5 | Sí |
| **26** | Ropa | 65.00 | 25 | 4.1 | Sí |
| **27** | Hogar | 95.00 | 10 | 4.3 | Sí |
| **28** | Deportes | 75.50 | 15 | 4.2 | No |
| **29** | Juguetes | 24.50 | 5 | 3.8 | No |
| **30** | Electrónica | 320.00 | 30 | 4.7 | Sí |
| **31** | Ropa | 22.90 | 0 | 3.5 | No |
| **32** | Hogar | 140.00 | 15 | 4.4 | Sí |
| **33** | Deportes | 50.00 | 10 | 4.0 | No |
| **34** | Juguetes | 19.99 | 10 | 3.7 | No |
| **35** | Electrónica | 150.00 | 15 | 4.3 | Sí |
| **36** | Ropa | 38.00 | 5 | 3.8 | No |
| **37** | Hogar | 85.00 | 0 | 4.1 | No |
| **38** | Deportes | 65.00 | 20 | 4.2 | Sí |
| **39** | Juguetes | 12.50 | 0 | 3.4 | No |
| **40** | Electrónica | 299.99 | 25 | 4.8 | Sí |
| **41** | Ropa | 48.00 | 15 | 4.0 | No |
| **42** | Hogar | 125.00 | 20 | 4.5 | Sí |
| **43** | Deportes | 35.00 | 10 | 3.9 | No |
| **44** | Juguetes | 27.00 | 5 | 3.8 | No |
| **45** | Electrónica | 199.00 | 15 | 4.4 | Sí |
| **46** | Ropa | 59.90 | 10 | 4.1 | No |
| **47** | Hogar | 79.90 | 5 | 4.0 | No |
| **48** | Deportes | 90.00 | 25 | 4.3 | Sí |
| **49** | Juguetes | 16.00 | 0 | 3.6 | No |
| **50** | Electrónica | 245.00 | 20 | 4.6 | Sí |
| **51** | Ropa | 33.50 | 5 | 3.7 | No |
| **52** | Hogar | 105.00 | 15 | 4.2 | Sí |
| **53** | Deportes | 42.00 | 0 | 3.9 | No |
| **54** | Juguetes | 21.90 | 10 | 3.7 | No |
| **55** | Electrónica | 110.00 | 10 | 4.1 | Sí |
| **56** | Ropa | 27.50 | 0 | 3.6 | No |
| **57** | Hogar | 99.00 | 15 | 4.3 | Sí |
| **58** | Deportes | 80.00 | 20 | 4.4 | Sí |
| **59** | Juguetes | 32.00 | 15 | 3.9 | No |
| **60** | Electrónica | 175.00 | 25 | 4.5 | Sí |
| **61** | Ropa | 52.00 | 10 | 3.9 | No |
| **62** | Hogar | 118.00 | 12 | 4.3 | Sí |
| **63** | Deportes | 58.00 | 5 | 4.0 | No |
| **64** | Juguetes | 14.90 | 0 | 3.5 | No |
| **65** | Electrónica | 220.00 | 15 | 4.6 | Sí |
| **66** | Ropa | 39.90 | 10 | 3.8 | No |
| **67** | Hogar | 88.00 | 10 | 4.1 | No |
| **68** | Deportes | 72.00 | 15 | 4.2 | Sí |
| **69** | Juguetes | 19.50 | 5 | 3.7 | No |
| **70** | Electrónica | 130.00 | 10 | 4.2 | Sí |
| **71** | Ropa | 45.00 | 0 | 3.8 | No |
| **72** | Hogar | 150.00 | 25 | 4.7 | Sí |
| **73** | Deportes | 64.00 | 10 | 4.1 | No |
| **74** | Juguetes | 25.00 | 15 | 3.8 | No |
| **75** | Electrónica | 180.00 | 20 | 4.4 | Sí |
| **76** | Ropa | 31.00 | 5 | 3.7 | No |
| **77** | Hogar | 92.50 | 10 | 4.2 | Sí |
| **78** | Deportes | 49.00 | 0 | 3.9 | No |
| **79** | Juguetes | 22.50 | 10 | 3.6 | No |
| **80** | Electrónica | 260.00 | 30 | 4.7 | Sí |
| **81** | Ropa | 42.50 | 15 | 3.9 | No |
| **82** | Hogar | 110.00 | 20 | 4.4 | Sí |
| **83** | Deportes | 38.00 | 5 | 3.8 | No |
| **84** | Juguetes | 29.90 | 10 | 3.9 | No |
| **85** | Electrónica | 145.00 | 15 | 4.3 | Sí |
| **86** | Ropa | 58.00 | 10 | 4.1 | No |
| **87** | Hogar | 76.00 | 0 | 4.0 | No |
| **88** | Deportes | 85.00 | 20 | 4.3 | Sí |
| **89** | Juguetes | 17.00 | 5 | 3.6 | No |
| **90** | Electrónica | 230.00 | 25 | 4.5 | Sí |
| **91** | Ropa | 35.00 | 0 | 3.7 | No |
| **92** | Hogar | 105.00 | 15 | 4.2 | Sí |
| **93** | Deportes | 55.00 | 10 | 4.0 | No |
| **94** | Juguetes | 20.00 | 10 | 3.7 | No |
| **95** | Electrónica | 125.00 | 10 | 4.1 | Sí |
| **96** | Ropa | 29.00 | 5 | 3.6 | No |
| **97** | Hogar | 97.00 | 15 | 4.3 | Sí |
| **98** | Deportes | 78.00 | 20 | 4.4 | Sí |
| **99** | Juguetes | 30.00 | 15 | 3.8 | No |
| **100** | Electrónica | 190.00 | 20 | 4.5 | Sí |
| **101** | Ropa | 49.90 | 10 | 3.9 | No |
| **102** | Hogar | 120.00 | 25 | 4.4 | Sí |
| **103** | Deportes | 60.00 | 10 | 4.1 | No |
| **104** | Juguetes | 15.00 | 0 | 3.5 | No |
| **105** | Electrónica | 210.00 | 15 | 4.6 | Sí |
| **106** | Ropa | 38.50 | 5 | 3.8 | No |
| **107** | Hogar | 82.00 | 10 | 4.0 | No |
| **108** | Deportes | 70.00 | 15 | 4.2 | Sí |
| **109** | Juguetes | 18.00 | 5 | 3.6 | No |
| **110** | Electrónica | 135.00 | 10 | 4.2 | Sí |
| **111** | Ropa | 44.00 | 0 | 3.8 | No |
| **112** | Hogar | 138.00 | 20 | 4.5 | Sí |
| **113** | Deportes | 62.00 | 10 | 4.0 | No |
| **114** | Juguetes | 23.00 | 10 | 3.7 | No |
| **115** | Electrónica | 165.00 | 15 | 4.3 | Sí |
| **116** | Ropa | 30.00 | 5 | 3.6 | No |
| **117** | Hogar | 89.00 | 10 | 4.1 | No |
| **118** | Deportes | 45.00 | 0 | 3.8 | No |
| **119** | Juguetes | 21.00 | 10 | 3.7 | No |
| **120** | Electrónica | 250.00 | 30 | 4.8 | Sí |
| **121** | Ropa | 41.00 | 10 | 3.9 | No |
| **122** | Hogar | 115.00 | 15 | 4.3 | Sí |
| **123** | Deportes | 36.00 | 5 | 3.7 | No |
| **124** | Juguetes | 28.00 | 15 | 3.9 | No |
| **125** | Electrónica | 150.00 | 15 | 4.3 | Sí |
| **126** | Ropa | 55.00 | 10 | 4.1 | No |
| **127** | Hogar | 78.00 | 0 | 4.0 | No |
| **128** | Deportes | 82.00 | 20 | 4.3 | Sí |
| **129** | Juguetes | 16.50 | 5 | 3.6 | No |
| **130** | Electrónica | 225.00 | 25 | 4.6 | Sí |
| **131** | Ropa | 34.00 | 0 | 3.7 | No |
| **132** | Hogar | 100.00 | 15 | 4.2 | Sí |
| **133** | Deportes | 52.00 | 10 | 4.0 | No |
| **134** | Juguetes | 19.00 | 10 | 3.6 | No |
| **135** | Electrónica | 120.00 | 10 | 4.1 | Sí |
| **136** | Ropa | 28.00 | 5 | 3.6 | No |
| **137** | Hogar | 95.00 | 15 | 4.3 | Sí |
| **138** | Deportes | 75.00 | 20 | 4.4 | Sí |
| **139** | Juguetes | 29.00 | 15 | 3.8 | No |
| **140** | Electrónica | 185.00 | 20 | 4.4 | Sí |
| **141** | Ropa | 48.00 | 10 | 3.9 | No |
| **142** | Hogar | 125.00 | 25 | 4.5 | Sí |
| **143** | Deportes | 58.00 | 10 | 4.1 | No |
| **144** | Juguetes | 14.50 | 0 | 3.4 | No |
| **145** | Electrónica | 205.00 | 15 | 4.6 | Sí |
| **146** | Ropa | 37.00 | 5 | 3.7 | No |
| **147** | Hogar | 80.00 | 10 | 4.0 | No |
| **148** | Deportes | 68.00 | 15 | 4.2 | Sí |
| **149** | Juguetes | 17.50 | 5 | 3.6 | No |
| **150** | Electrónica | 130.00 | 10 | 4.1 | Sí |
| **151** | Ropa | 42.00 | 0 | 3.8 | No |
| **152** | Hogar | 130.00 | 20 | 4.4 | Sí |
| **153** | Deportes | 60.00 | 10 | 4.0 | No |
| **154** | Juguetes | 22.00 | 10 | 3.7 | No |
| **155** | Electrónica | 160.00 | 15 | 4.3 | Sí |
| **156** | Ropa | 29.50 | 5 | 3.6 | No |
| **157** | Hogar | 85.00 | 10 | 4.1 | No |
| **158** | Deportes | 44.00 | 0 | 3.8 | No |
| **159** | Juguetes | 20.50 | 10 | 3.6 | No |
| **160** | Electrónica | 240.00 | 30 | 4.7 | Sí |
| **161** | Ropa | 39.50 | 10 | 3.8 | No |
| **162** | Hogar | 110.00 | 15 | 4.3 | Sí |
| **163** | Deportes | 35.00 | 5 | 3.7 | No |
| **164** | Juguetes | 27.50 | 15 | 3.9 | No |
| **165** | Electrónica | 145.00 | 15 | 4.2 | Sí |
| **166** | Ropa | 54.00 | 10 | 4.1 | No |
| **167** | Hogar | 75.00 | 0 | 4.0 | No |
| **168** | Deportes | 80.00 | 20 | 4.3 | Sí |
| **169** | Juguetes | 16.00 | 5 | 3.5 | No |
| **170** | Electrónica | 220.00 | 25 | 4.6 | Sí |
| **171** | Ropa | 33.00 | 0 | 3.7 | No |
| **172** | Hogar | 98.00 | 15 | 4.2 | Sí |
| **173** | Deportes | 50.00 | 10 | 3.9 | No |
| **174** | Juguetes | 18.50 | 10 | 3.6 | No |
| **175** | Electrónica | 115.00 | 10 | 4.0 | Sí |
| **176** | Ropa | 27.00 | 5 | 3.5 | No |
| **177** | Hogar | 92.00 | 15 | 4.3 | Sí |
| **178** | Deportes | 72.00 | 20 | 4.4 | Sí |
| **179** | Juguetes | 28.50 | 15 | 3.8 | No |
| **180** | Electrónica | 180.00 | 20 | 4.4 | Sí |
| **181** | Ropa | 46.00 | 10 | 3.9 | No |
| **182** | Hogar | 120.00 | 25 | 4.5 | Sí |
| **183** | Deportes | 55.00 | 10 | 4.0 | No |
| **184** | Juguetes | 14.00 | 0 | 3.4 | No |
| **185** | Electrónica | 199.00 | 15 | 4.5 | Sí |
| **186** | Ropa | 36.00 | 5 | 3.7 | No |
| **187** | Hogar | 79.00 | 10 | 4.0 | No |
| **188** | Deportes | 65.00 | 15 | 4.1 | Sí |
| **189** | Juguetes | 17.00 | 5 | 3.6 | No |
| **190** | Electrónica | 125.00 | 10 | 4.1 | Sí |
| **191** | Ropa | 40.00 | 0 | 3.8 | No |
| **192** | Hogar | 125.00 | 20 | 4.4 | Sí |
| **193** | Deportes | 58.00 | 10 | 4.0 | No |
| **194** | Juguetes | 21.50 | 10 | 3.7 | No |
| **195** | Electrónica | 155.00 | 15 | 4.3 | Sí |
| **196** | Ropa | 29.00 | 5 | 3.6 | No |
| **197** | Hogar | 82.00 | 10 | 4.1 | No |
| **198** | Deportes | 42.00 | 0 | 3.8 | No |
| **199** | Juguetes | 19.90 | 10 | 3.6 | No |
| **200** | Electrónica | 235.00 | 30 | 4.7 | Sí |
| **201** | Ropa | 38.00 | 10 | 3.8 | No |
| **202** | Hogar | 105.00 | 15 | 4.2 | Sí |
| **203** | Deportes | 34.00 | 5 | 3.7 | No |
| **204** | Juguetes | 26.00 | 15 | 3.9 | No |
| **205** | Electrónica | 140.00 | 15 | 4.2 | Sí |
| **206** | Ropa | 52.00 | 10 | 4.1 | No |
| **207** | Hogar | 72.00 | 0 | 4.0 | No |
| **208** | Deportes | 78.00 | 20 | 4.3 | Sí |
| **209** | Juguetes | 15.50 | 5 | 3.5 | No |
| **210** | Electrónica | 215.00 | 25 | 4.6 | Sí |
| **211** | Ropa | 32.00 | 0 | 3.7 | No |
| **212** | Hogar | 95.00 | 15 | 4.2 | Sí |
| **213** | Deportes | 48.00 | 10 | 3.9 | No |
| **214** | Juguetes | 18.00 | 10 | 3.6 | No |
| **215** | Electrónica | 110.00 | 10 | 4.0 | Sí |
| **216** | Ropa | 26.50 | 5 | 3.5 | No |
| **217** | Hogar | 89.00 | 15 | 4.3 | Sí |
| **218** | Deportes | 70.00 | 20 | 4.4 | Sí |
| **219** | Juguetes | 27.50 | 15 | 3.8 | No |
| **220** | Electrónica | 175.00 | 20 | 4.4 | Sí |
| **221** | Ropa | 44.50 | 10 | 3.9 | No |
| **222** | Hogar | 115.00 | 25 | 4.5 | Sí |
| **223** | Deportes | 52.00 | 10 | 4.0 | No |
| **224** | Juguetes | 13.50 | 0 | 3.4 | No |
| **225** | Electrónica | 195.00 | 15 | 4.5 | Sí |
| **226** | Ropa | 35.00 | 5 | 3.7 | No |
| **227** | Hogar | 76.00 | 10 | 4.0 | No |
| **228** | Deportes | 62.00 | 15 | 4.1 | Sí |
| **229** | Juguetes | 16.50 | 5 | 3.6 | No |
| **230** | Electrónica | 120.00 | 10 | 4.1 | Sí |
| **231** | Ropa | 38.50 | 0 | 3.8 | No |
| **232** | Hogar | 120.00 | 20 | 4.4 | Sí |
| **233** | Deportes | 55.00 | 10 | 4.0 | No |
| **234** | Juguetes | 21.00 | 10 | 3.7 | No |
| **235** | Electrónica | 150.00 | 15 | 4.3 | Sí |
| **236** | Ropa | 28.50 | 5 | 3.6 | No |
| **237** | Hogar | 80.00 | 10 | 4.1 | No |
| **238** | Deportes | 40.00 | 0 | 3.8 | No |
| **239** | Juguetes | 19.50 | 10 | 3.6 | No |
| **240** | Electrónica | 230.00 | 30 | 4.7 | Sí |
| **241** | Ropa | 37.00 | 10 | 3.8 | No |
| **242** | Hogar | 100.00 | 15 | 4.2 | Sí |
| **243** | Deportes | 33.00 | 5 | 3.7 | No |
| **244** | Juguetes | 25.00 | 15 | 3.9 | No |
| **245** | Electrónica | 135.00 | 15 | 4.2 | Sí |
| **246** | Ropa | 50.00 | 10 | 4.1 | No |
| **247** | Hogar | 70.00 | 0 | 4.0 | No |
| **248** | Deportes | 75.00 | 20 | 4.3 | Sí |
| **249** | Juguetes | 15.00 | 5 | 3.5 | No |
| **250** | Electrónica | 210.00 | 25 | 4.6 | Sí |
| **251** | Ropa | 31.50 | 0 | 3.7 | No |
| **252** | Hogar | 92.00 | 15 | 4.2 | Sí |
| **253** | Deportes | 46.00 | 10 | 3.9 | No |
| **254** | Juguetes | 17.50 | 10 | 3.6 | No |
| **255** | Electrónica | 105.00 | 10 | 4.0 | Sí |
| **256** | Ropa | 26.00 | 5 | 3.5 | No |
| **257** | Hogar | 86.00 | 15 | 4.3 | Sí |
| **258** | Deportes | 68.00 | 20 | 4.4 | Sí |
| **259** | Juguetes | 26.50 | 15 | 3.8 | No |
| **260** | Electrónica | 170.00 | 20 | 4.4 | Sí |
| **261** | Ropa | 43.00 | 10 | 3.9 | No |
| **262** | Hogar | 110.00 | 25 | 4.5 | Sí |
| **263** | Deportes | 50.00 | 10 | 4.0 | No |
| **264** | Juguetes | 13.00 | 0 | 3.4 | No |
| **265** | Electrónica | 190.00 | 15 | 4.5 | Sí |
| **266** | Ropa | 34.00 | 5 | 3.7 | No |
| **267** | Hogar | 74.00 | 10 | 4.0 | No |
| **268** | Deportes | 60.00 | 15 | 4.1 | Sí |
| **269** | Juguetes | 16.00 | 5 | 3.6 | No |
| **270** | Electrónica | 115.00 | 10 | 4.1 | Sí |
| **271** | Ropa | 37.50 | 0 | 3.8 | No |
| **272** | Hogar | 115.00 | 20 | 4.4 | Sí |
| **273** | Deportes | 52.00 | 10 | 4.0 | No |
| **274** | Juguetes | 20.00 | 10 | 3.7 | No |
| **275** | Electrónica | 145.00 | 15 | 4.3 | Sí |
| **276** | Ropa | 28.00 | 5 | 3.6 | No |
| **277** | Hogar | 78.00 | 10 | 4.1 | No |
| **278** | Deportes | 38.00 | 0 | 3.8 | No |
| **279** | Juguetes | 19.00 | 10 | 3.6 | No |
| **280** | Electrónica | 225.00 | 30 | 4.7 | Sí |
| **281** | Ropa | 36.00 | 10 | 3.8 | No |
| **282** | Hogar | 98.00 | 15 | 4.2 | Sí |
| **283** | Deportes | 32.00 | 5 | 3.7 | No |
| **284** | Juguetes | 24.00 | 15 | 3.9 | No |
| **285** | Electrónica | 130.00 | 15 | 4.2 | Sí |
| **286** | Ropa | 48.00 | 10 | 4.1 | No |
| **287** | Hogar | 68.00 | 0 | 4.0 | No |
| **288** | Deportes | 72.00 | 20 | 4.3 | Sí |
| **289** | Juguetes | 14.50 | 5 | 3.5 | No |
| **290** | Electrónica | 205.00 | 25 | 4.6 | Sí |
| **291** | Ropa | 30.50 | 0 | 3.7 | No |
| **292** | Hogar | 89.00 | 15 | 4.2 | Sí |
| **293** | Deportes | 44.00 | 10 | 3.9 | No |
| **294** | Juguetes | 17.00 | 10 | 3.6 | No |
| **295** | Electrónica | 100.00 | 10 | 4.0 | Sí |
| **296** | Ropa | 25.50 | 5 | 3.5 | No |
| **297** | Hogar | 82.00 | 15 | 4.3 | Sí |
| **298** | Deportes | 65.00 | 20 | 4.4 | Sí |
| **299** | Juguetes | 25.50 | 15 | 3.8 | No |
| **300** | Electrónica | 165.00 | 20 | 4.4 | Sí |

</details>

---

## 3. Técnica de Minería de Datos Aplicada
* **Algoritmo:** Árbol de Decisión (Clasificación binaria).
* **División de datos:** 80% entrenamiento, 20% prueba.
* **Resultado obtenido:** Precisión general (Accuracy) de 51.67%.

## 4. Conclusiones y Recomendaciones
* **Insight principal:** Con las variables actuales, el modelo tiene un rendimiento cercano al azar. Esto nos indica que el éxito de ventas en e-commerce es un fenómeno complejo que no depende únicamente del precio o la categoría.
* **Limitaciones:** Dataset acotado a 300 registros sintéticos.
* **Recomendaciones futuras:** Incorporar variables cualitativas como "comentarios de clientes", "gasto en publicidad" o "mes de venta" (estacionalidad) para mejorar la precisión del modelo.

## 5. Video Explicativo del Proyecto
* [Haz clic aquí para ver el video explicativo](Pega_aquí_el_enlace_de_tu_video)
  
* **Tamaño:** 300 registros (productos).
* **Proceso de Limpieza con IA:**
  * Homogeneización de texto en la variable `Categoria` (corrección de mayúsculas/minúsculas).
  * Imputación de precios erróneos (valores negativos de -99.0) utilizando la mediana por categoría.
  * Rellenado de valores nulos (`NaN`) en `Calificacion` con el promedio general.
  * Creación de la variable objetivo binaria `Exito_Ventas`.


## 3. Técnica de Minería de Datos Aplicada
* **Algoritmo:** Árbol de Decisión (Clasificación binaria).
* **División de datos:** 80% entrenamiento, 20% prueba.
* **Resultado obtenido:** Precisión general (Accuracy) de 51.67%.

## 4. Conclusiones y Recomendaciones
* **Insight principal:** Con las variables actuales, el modelo tiene un rendimiento cercano al azar. Esto nos indica que el éxito de ventas en e-commerce es un fenómeno complejo que no depende únicamente del precio o la categoría.
* **Limitaciones:** Dataset acotado a 300 registros sintéticos.
* **Recomendaciones futuras:** Incorporar variables cualitativas como "comentarios de clientes", "gasto en publicidad" o "mes de venta" (estacionalidad) para mejorar la precisión del modelo.

## 5. Video Explicativo del Proyecto
* [Haz clic aquí para ver el video explicativo](Pega_aquí_el_enlace_de_tu_video)

* **Tamaño:** 300 registros (productos).
* **Proceso de Limpieza con IA:**
  * Homogeneización de texto en la variable `Categoria` (corrección de mayúsculas/minúsculas).
  * Imputación de precios erróneos (valores negativos de -99.0) utilizando la mediana por categoría.
  * Rellenado de valores nulos (`NaN`) en `Calificacion` con el promedio general.
  * Creación de la variable objetivo binaria `Exito_Ventas`.

## 3. Técnica de Minería de Datos Aplicada
* **Algoritmo:** Árbol de Decisión (Clasificación binaria).
* **División de datos:** 80% entrenamiento, 20% prueba.
* **Resultado obtenido:** Precisión general (Accuracy) de 51.67%.

### Visualización del Análisis de Datos:
<img width="1667" height="582" alt="image" src="https://github.com/user-attachments/assets/95403624-a277-4ea3-87bd-46d4d7ddb2c4" />


## 4. Conclusiones y Recomendaciones
* **Insight principal:** Con las variables actuales, el modelo tiene un rendimiento cercano al azar. Esto nos indica que el éxito de ventas en e-commerce es un fenómeno complejo que no depende únicamente del precio o la categoría.
* **Limitaciones:** Dataset acotado a 300 registros sintéticos.
* **Recomendaciones futuras:** Incorporar variables cualitativas como "comentarios de clientes", "gasto en publicidad" o "mes de venta" (estacionalidad) para mejorar la precisión del modelo.

## 5. Video Explicativo del Proyecto
* [Haz clic aquí para ver el video explicativo](Pega_aquí_el_enlace_de_tu_video)
