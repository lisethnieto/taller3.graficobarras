# taller3.graficobarras
import pandas as pd 
import matplotlib.pyplot as plt
import numpy as np

data = pd.DataFrame({'Mujeres' : [326, 543, 242, 101],
                     'Hombres': [568, 881, 391, 3],
                     'Poblaciontrans': [288, 53, 63, 37],
                     'transexuales': [88, 3, 33, 100]},
                    index=('Ingenieria', 'Medicina', 'Economia', 'Matematicas'))



n = len(data.index)
x = np.arange(n)
width = 0.20

plt.bar(x + 2*width, data.Mujeres, width=width, label='Mujeres')
plt.bar(x + width, data.Hombres, width=width, label='Hombres')
plt.bar(x, data.Poblaciontrans, width=width, label='Poblacion-trans')
plt.bar(x - width, data.transexuales, width=width, label='transexuales')
plt.xticks(x, data.index)
plt.title("poblacion estudiantil -udea")
plt.legend(loc='best')
plt.show()

fig, ax = plt.subplots(5, 2, sharey = True)
ax[0, 0].bar(x + 2*width, data.Mujeres, width=width, label='Mujeres')
ax[1, 0].bar(x + width, data.Hombres, width=width, label='Hombres',color = 'tab:orange')
ax[2, 0].bar(x, data.Poblaciontrans, width=width, label='Poblacion-trans',color = 'tab:green')
ax[3, 0].bar(x, data.transexuales, width=width, label='Poblacion-trans',color = 'tab:red')
ax[4, 0].bar(x, data.Poblaciontrans, width=width, label='Poblacion-trans',color='tab:green')
ax[4, 0].bar(x + 2*width, data.Mujeres, width=width, label='Mujeres')
ax[4, 0].bar(x + width, data.Hombres, width=width, label='Hombres',color = 'tab:orange')
ax[4, 0].bar(x, data.transexuales, width=width, label='Poblacion-trans',color = 'tab:red')
ax[0, 1].plot(x , data.Mujeres, label='Mujeres')
ax[1, 1].plot(x , data.Hombres, label='Hombres',color = 'tab:orange')
ax[2, 1].plot(x, data.Poblaciontrans, label='Poblacion-trans',color = 'tab:green')
ax[3, 1].plot(x, data.transexuales, label='Poblacion-trans',color = 'tab:red')
ax[4, 1].plot(x, data.Poblaciontrans, label='Poblacion-trans',color='tab:green')
ax[4, 1].plot(x, data.Mujeres, label='Mujeres')
ax[4, 1].plot(x, data.Hombres, label='Hombres',color = 'tab:orange')
ax[4, 1].plot(x, data.transexuales, label='Poblacion-trans',color = 'tab:red')
plt.show()
