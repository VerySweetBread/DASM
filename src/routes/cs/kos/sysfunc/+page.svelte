<script lang="ts">
  import { Accordion, AccordionItem } from '@skeletonlabs/skeleton';
  import { CodeBlock } from '@skeletonlabs/skeleton';
</script>


<Accordion autocollapse>
  <AccordionItem>
    <svelte:fragment slot="lead">-1</svelte:fragment>
    <svelte:fragment slot="summary">Завершить выполнение потока/процесса <span class="badge variant-filled-secondary">Процессы и потоки</span></svelte:fragment>
    <svelte:fragment slot="content">
      Функция ничего не принимает и ничего не возвращает
    </svelte:fragment>
  </AccordionItem>
  <AccordionItem>
    <svelte:fragment slot="lead">0</svelte:fragment>
    <svelte:fragment slot="summary">Определить и нарисовать окно <span class="badge variant-filled-secondary">Оконный интерфейс</span></svelte:fragment>
    <svelte:fragment slot="content">
      <blockquote class="blockquote">
        Определяет окно приложения. Рисует рамку окна, заголовок и рабочую область. Для окон со скином определяет стандартные кнопки закрытия и минимизации
      </blockquote>
      <div class="table-container">
        <!-- Native Table Element -->
        <table class="table table-hover">
          <thead>
            <tr>
              <th>Регистр</th>
              <th>Описание</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td><span class="badge variant-filled">EBX</span></td>
              <td>[координата по оси x]*65536 + [размер по оси x]</td>
            </tr>
            <tr>
              <td><span class="badge variant-filled">ECX</span></td>
              <td>[координата по оси y]*65536 + [размер по оси y]</td>
            </tr>
            <tr>
              <td><span class="badge variant-filled">EDX</span></td>
              <td>
                <code class="code">0xXYRRGGBB</code>
                <div class="table-container">
                  <table class="table table-hover">
                    <tbody>
                      <tr>
                        <td><span class="badge variant-ghost-surface">X</span></td>
                        <td><code class="code">DCBA</code> (биты)
                          <div class="table-container">
                            <table class="table table-hover">
                              <tbody>
                                <tr>
                                  <td><span class="badge variant-ghost-surface">D</span></td>
                                  <td>
                                    <p>0 — нормальная заливка рабочей области</p>
                                    <p>1 — градиентная</p>
                                  </td>
                                </tr>
                                <tr>
                                  <td><span class="badge variant-ghost-surface">C</span></td>
                                  <td>1 — не закрашивать рабочую область при отрисовке окна</td>
                                </tr>
                                <tr>
                                  <td><span class="badge variant-ghost-surface">B</span></td>
                                  <td>1 — координаты всех графических примитивов задаются
                                    относительно клиентской области окна</td>
                                </tr>
                                <tr>
                                  <td><span class="badge variant-ghost-surface">A</span></td>
                                  <td>
                                    <p>1 — у окна есть заголовок;</p> 
                                    <p>
                                      Для стилей 
                                      <span class="badget variant-soft-surface">Y=3,4</span>
                                       адрес строки заголовка задаётся в 
                                      <span class="badge variant-filled">EDI</span>
                                    </p>
                                    <p>Для прочих стилей используется 
                                      <a href="#71.1">
                                        <span class="badge variant-filled-tertiary">ф71.1</span>
                                      </a>
                                    </p>
                                  </td>
                                </tr>
                              </tbody>
                            </table>
                          </div>
                        </td>
                      </tr>
                      <tr>
                        <td><span class="badge variant-ghost-surface">Y</span></td>
                        <td>
                          Стиль окна
                          <div class="table-container">
                            <table class="table table-hover">
                              <tbody>
                                <tr>
                                  <td><span class="badge variant-ghost-surface">0</span></td>
                                  <td>
                                    <span class="badge variant-soft">тип I</span>
                                    Окно фиксированных размеров
                                  </td>
                                </tr>
                                <tr>
                                  <td><span class="badge variant-ghost-surface">1</span></td>
                                  <td>Только определить область окна, ничего не рисовать<td>
                                </tr>
                                <tr>
                                  <td><span class="badge variant-ghost-surface">2</span></td>
                                  <td><span class="badge variant-soft">тип II</span> Окно изменяемых размеров</td>
                                </tr>
                                <tr>
                                  <td><span class="badge variant-ghost-surface">3</span></td>
                                  <td>Окно со скином</td>
                                </tr>
                                <tr>
                                  <td><span class="badge variant-ghost-surface">4</span></td>
                                  <td>Окно со скином фиксированных размеров</td>
                                </tr>
                                <tr>
                                  <td><span class="badge variant-ghost-surface">5-15</span></td>
                                  <td>Зарезервированы, вызов функции с такими Y игнорируется</td>
                                </tr>
                              </tbody>
                            </table>
                          </div>
                        </td>
                      </tr>
                      <tr>
                        <td><span class="badge variant-ghost-surface">RRGGBB</span></td>
                        <td>
                          <p>Цвета рабочей области окна</p>
                          <p>игнорируется для стиля <span class="badget variant-soft-surface">Y=1</span></p>
                        </td>
                      </tr>
                    </tbody>
                  </table>
                </div>
              </td>
            </tr>
            <tr>
              <td><span class="badge variant-filled">ESI</span></td>
              <td>
                Заголовок — <code class="code">0xXYRRGGBB</code>
                <div class="table-container">
                  <table class="table table-hover">
                    <tbody>
                      <tr>
                        <td><span class="badge variant-ghost-surface">X</span></td>
                        <td>
                          <p>Градиент заголовка</p>
                          <div class="table-container">
                            <table class="table table-hover">
                              <tbody>
                                <tr>
                                  <td><span class="badge variant-ghost-surface">0</span></td>
                                  <td>Нет градиента</td>
                                </tr>
                                <tr>
                                  <td><span class="badge variant-ghost-surface">8</span></td>
                                  <td>Обычный градиент</td>
                                </tr>
                              </tbody>
                            </table>
                          </div>
                          <p>Для <span class="badget variant-soft-surface">Тип II X=4</span> негативный градиент<p>
                        </td>
                      </tr>
                      <tr>
                        <td><span class="badge variant-ghost-surface">Y</span></td>
                        <td>
                          <div class="table-container">
                            <table class="table table-hover">
                              <tbody>
                                <tr>
                                  <td><span class="badge variant-ghost-surface">0</span></td>
                                  <td>Обычное окно</td>
                                </tr>
                                <tr>
                                  <td><span class="badge variant-ghost-surface">1</span></td>
                                  <td>Неперемещаемое окно</td>
                                </tr>
                              </tbody>
                            </table>
                          </div>
                        </td>
                      </tr>
                      <tr>
                        <td><span class="badge variant-ghost-surface">RRGGBB</span></td>
                        <td>Цвет заголовка</td>
                      </tr>
                    </tbody>
                  </table>
                </div>
              </td>
            </tr>
            <tr>
              <td><span class="badge variant-filled">EDI</span></td>
              <td>Цвет рамки — <code class="code">0x00RRGGBB</code></td>
            </tr>
          </tbody>
        </table>
      </div>
    </svelte:fragment>
  </AccordionItem>
  <AccordionItem>
    <svelte:fragment slot="lead">1</svelte:fragment>
    <svelte:fragment slot="summary">Поставить точку в окне <span class="badge variant-filled-secondary">Графика</span></svelte:fragment>
    <svelte:fragment slot="content">
      <div class="table-container">
        <table class="table table-hover">
          <thead>
            <th>Регистр</th>
            <th>Описание</th>
          </thead>
          <tbody>
            <tr>
              <td><span class="badge variant-filled">EBX</span></td>
              <td>x-координата (относительно окна)</td>
            </tr>
            <tr>
              <td><span class="badge variant-filled">ECX</span></td>
              <td>y-координата (относительно окна)</td>
            </tr>
            <tr>
              <td><span class="badge variant-filled">EDX</span></td>
              <td>
                <p><code class="code">0x00RRGGBB</code> - цвет точки</p>
                <p><code class="code">0x01xxxxxx</code> - инвертировать цвет точки (младшие 24 бита игнорируются)</p>
              </td>
            </tr>
          </tbody>
    </svelte:fragment>
  </AccordionItem>
  <AccordionItem>
    <svelte:fragment slot="lead">2</svelte:fragment>
    <svelte:fragment slot="summary">Получить код нажатой клавиши <span class="badge variant-filled-secondary">Ввод</span></svelte:fragment>
    <svelte:fragment slot="content">
      <blockquote class="blockquote">
        Забирает код нажатой клавиши из буфера
      </blockquote>
      <div class="table-container">
        <table class="table table-hover">
          <tbody>
            <tr>
              <td><span class="badge variant-filled-success">Возвращаемое значение</span></td>
              <td>
                <div class="table-container">
                  <table class="table table-hover">
                    <thead>
                      <tr>
                        <th>Условие</th>
                        <th>Возвращаемое значение</th>
                      </tr>
                    </thead>
                    <tbody>
                      <tr>
                        <td>Если буфер пуст</td>
                        <td>EAX=1</td>
                      </tr>
                      <tr>
                        <td>Если буфер непуст</td>
                        <td>
                          <p>AL=0, AH=код нажатой клавиши</p>
                          <p>биты 16-23 содержат сканкод нажатой клавиши в режиме ASCII</p>
                          <p>в режиме сканкодов биты обнулены.</p>
                          <p>биты 23-31 обнулены</p>
                        </td>
                      </tr>
                      <tr>
                        <td>Если есть "горячая клавиша"</td>
                        <td>
                          <p>AL=2, AH=сканкод нажатой клавиши (0 для управляющих клавиш)</p>
                          <p>Старшее слово регистра eax содержит состояние управляющих клавиш в момент нажатия горячей клавиши</p>
                        </td>
                      </tr>
                    </tbody>
                  </table>
                </div>
              </td>
            </tr>
          </tbody>
        </table>
      </div>
    </svelte:fragment>
  </AccordionItem>
  <AccordionItem>
    <svelte:fragment slot="lead">3</svelte:fragment>
    <svelte:fragment slot="summary">Получить системное время <span class="badge variant-filled-secondary">Системный сервис</span></svelte:fragment>
    <svelte:fragment slot="content">
      <div class="table-container">
        <table class="table table-hover">
          <tbody>
            <tr>
              <td><span class="badge variant-filled-success">Возвращаемые значения</span></td>
              <td>
                <div class="table-container">
                  <table class="table table-hover">
                    <tbody>
                      <tr>
                        <td><span class="badge variant-filled">EAX</span></td>
                        <td>
                          <p><code class="code">0x00SSMMHH</code>, где HH:MM:SS = часы:минуты:секунды</p>
                          <p>Каждый элемент возвращается как BCD-число, например, для времени 23:59:59 результат будет <code class="code">0x00595923</code></p>
                        </td>
                      <td>
                    </tbody>
                  </table>
                </div>
              </td>
            </tr>
          </tbody>
        </table>
      </div>
    </svelte:fragment>
  </AccordionItem>
  <AccordionItem>
    <svelte:fragment slot="lead">4</svelte:fragment>
    <svelte:fragment slot="summary">Вывести строку текста в окно <span class="badge variant-filled-secondary">Графика</span></svelte:fragment>
    <svelte:fragment slot="content">
      <div class="table-container">
        <table class="table table-hover">
          <thead>
            <tr>
              <th>Регистры</th>
              <th>Описание</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td><span class="badge variant-filled">EBX</span></td>
              <td>[координата по оси x]*65536 + [координата по оси y]</td>
            </tr>
            <tr>
              <td><span class="badge variant-filled">ECX</span></td>
              <td><code class="code">0xXXRRGGBB</code>
                <div class="table-container">
                  <table class="table table-hover">
                    <tbody>
                      <tr>
                        <td><span class="badge variant-soft-surface">XX</span></td>
                        <td><code class="code">ABFFCSSS</code> (биты)
                          <div class="table-container">
                            <table class="table table-hover">
                              <tbody>
                                <tr>
                                  <td><span class="badge variant-soft-surface">A</span></td>
                                  <td>1 - рисуемая строка заканчивается нулём</td>
                                </tr>
                                <tr>
                                  <td><span class="badge variant-soft-surface">B</span></td>
                                  <td>1 - закрашивать фон (цвет = <span class="badge variant-filled">EDI</span>)</td>
                                </tr>
                                <tr>
                                  <td><span class="badge variant-soft-surface">FF</span></td>
                                  <div class="table-container">
                                    <table class="table table-hover">
                                      <tbody>
                                        <tr>
                                          <td><span class="badge variant-soft-surface">0</span></td>
                                          <td>6x9 cp866</td>
                                        </tr>
                                        <tr>
                                          <td><span class="badge variant-soft-surface">1</span></td>
                                          <td>8x16 cp866</td>
                                        </tr>
                                        <tr>
                                          <td><span class="badge variant-soft-surface">2</span></td>
                                          <td>8x16 UTF-16LE</td>
                                        </tr>
                                        <tr>
                                          <td><span class="badge variant-soft-surface">3</span></td>
                                          <td>8x16 UTF-8</td>
                                        </tr>
                                      </tbody>
                                    </table>
                                  </div>
                                </tr>
                                <tr>
                                  <td><span class="badge variant-soft-surface">C</span></td>
                                  <td>
                                    <div class="table-container">
                                      <table class="table table-hover">
                                        <tbody>
                                          <tr>
                                            <td><span class="badge variant-soft-surface">0</span></td>
                                            <td>Рисовать в окно</td>
                                          </tr>
                                          <tr>
                                            <td><span class="badge variant-soft-surface">1</span></td>
                                            <td>Рисовать в буфер <span class="badge variant-filled">EDI</span></td>
                                          </tr>
                                        </tbody>
                                      </table>
                                    </div>
                                  </td>
                                </tr>
                                <tr>
                                  <td><span class="badge variant-soft-surface">SSS</span></td>
                                  <td>
                                    <p>множитель размера</p>
                                    <p>0 = x1, 7 = x8</p>
                                  </td>
                                </tr>
                              </tbody>
                            </table>
                          </div>
                        </td>
                      </tr>
                      <tr>
                        <td><span class="badge variant-soft-surface">RRGGBB</span></td>
                        <td>Цвет текста</td>
                      </tr>
                    </tbody>
                  </table>
                </div>
              </td>
            </tr>
            <tr>
              <td><span class="badge variant-filled">EDX</span></td>
              <td>Указатель на начало строки</td>
            </tr>
            <tr>
              <td><span class="badge variant-filled">ESI</span></td>
              <td>Длина строки (при A=0)</td>
            </tr>
            <tr>
              <td><span class="badge variant-filled">EDI</span></td>
              <td>
                <div class="table-container">
                  <table class="table table-hover">
                    <tbody>
                      <tr>
                        <td>Если B=1</td>
                        <td>Цвет для закраски фона</td>
                      </tr>
                      <tr>
                        <td>Если C=1</td>
                        <td>Указатель на буфер</td>
                      </tr>
                    </tbody>
                  </table>
                </div>
              </td>
            </tr>
          </tbody>
          <tfoot>
            <tr>
              <td><span class="badge variant-filled-warning">Замечания</span></td>
              <td>
                <div class="table-container">
                  <table class="table table-hover">
                    <tbody>
                      <tr>
                        <td>Структура буфера</td>
                        <td>
                          <CodeBlock language="x86asm" code={`
Xsize dd ?
Ysize dd ?
picture rb Xsize * Ysize * 4 ; 32 бита
                          `} />
                        </td>
                      </tr>
                    </tbody>
                  </table>
                </div> 
              </td>
            </tr>
          </tfoot>
        </table>
      </div>
    </svelte:fragment>
  </AccordionItem>
  <AccordionItem>
    <svelte:fragment slot="lead">5</svelte:fragment>
    <svelte:fragment slot="summary">Пауза <span class="badge variant-filled-secondary">Процессы и потоки</span></svelte:fragment>
    <svelte:fragment slot="content">
      <blockquote class="blockquote">
        Задерживает выполнение программы на заданное время
      </blockquote>
      <div class="table-container">
        <table class="table table-hover">
          <thead>
            <tr>
              <th>Регистры</th>
              <th>Описание</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td><span class="badge variant-filled">EBX</span></td>
              <td>Время в сотых долях секунды</td>
            </tr>
          </tbody>
        </table>
      </div> 
    </svelte:fragment>
  </AccordionItem>
  <AccordionItem>
    <svelte:fragment slot="lead">7</svelte:fragment>
    <svelte:fragment slot="summary">Вывести изображение в окно <span class="badge variant-filled-secondary">Графика</span></svelte:fragment>
    <svelte:fragment slot="content">
      <div class="table-container">
        <table class="table table-hover">
          <thead>
            <tr>
              <th>Регистры</th>
              <th>Описание</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td><span class="badge variant-filled">EBX</span></td>
              <td>указатель на изображение в формате BBGGRRBBGGRR...</td>
            </tr>
            <tr>
              <td><span class="badge variant-filled">ECX</span></td>
              <td>[размер по оси x]*65536 + [размер по оси y]</td>
            </tr>
            <tr>
              <td><span class="badge variant-filled">EDX</span></td>
              <td>[координата по оси x]*65536 + [координата по оси y]</td>
            </tr>
          </tbody>
        </table>
      </div>
    </svelte:fragment>
  </AccordionItem>
</Accordion>
