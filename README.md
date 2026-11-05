# Macau: law history in git

The law of Macau as a git history: one file per provision, and the law that made each change as the commit's author, so `git blame` names the law behind every line.

It follows the shared design of [lexifina/global-law](https://github.com/lexifina/global-law), which places it at `mo/`.

**What is in it now (first build retrieved 2026-10-29; codes added 2026-10-31)**

| Folder | Law | Versions | Language |
| --- | --- | ---: | --- |
| `basic-law/` | Basic Law of the Macao SAR (preamble and Articles 1 to 145), implemented 20 December 1999 | 1 | Chinese (traditional); the Basic Law is authentic in Chinese and Portuguese |
| `annexes/` | Annexes I to III, with the 2012 amendments shown beside the original text | 1 | Chinese (traditional) |
| `codigo-penal/` | Código Penal (Decreto-Lei n.º 58/95/M), updated text as published by the Imprensa Oficial in the Boletim Oficial pages, as shown on 16 August 2025 | 1 | Portuguese, an official language of Macau |
| `codigo-processo-penal/` | Código de Processo Penal (Decreto-Lei n.º 48/96/M), updated text as published by the Imprensa Oficial in the Boletim Oficial pages, as shown on 28 August 2025 | 1 | Portuguese |
| `lei-relacoes-trabalho/` | Lei n.º 7/2008, Lei das relações de trabalho (labour relations law), updated text as published by the Imprensa Oficial in the Boletim Oficial pages, as shown on 3 April 2025 | 1 | Portuguese |
| `codigo-civil/` | Código Civil (Decreto-Lei n.º 39/99/M), updated text as published by the Imprensa Oficial in the Boletim Oficial pages, as shown on 13 February 2025 | 1 | Portuguese |
| `codigo-comercial/` | Código Comercial (Decreto-Lei n.º 40/99/M), updated text as published by the Imprensa Oficial in the Boletim Oficial pages, as shown on 17 September 2025 | 1 | Portuguese |

Sources: the Legislative Assembly of the Macao SAR website (Basic Law, in Chinese) and the Boletim Oficial of the Imprensa Oficial (codes and laws, in Portuguese). Each code or law is the updated text the Imprensa Oficial shows, with its footnotes pointing to amending laws left out; there is no dated history yet, and the Chinese texts of the codes are not built.

This is a first, small build, not the whole statute book. It has no dated history: each act is one "oldest version available" commit, dated from the source's own date and credited to the publisher. Texts are in the official language shown above; the English is a translation where marked, and the original governs.

Sources and terms are in `LICENSE`; how it was built is in `REPRODUCE.md`. Not legal advice; for anything that matters, read the original.

## Additional Assembly laws

The following Portuguese official gazette publications have one whole-act text file each. Chinese terms quoted in the Portuguese text are retained. Their original wording has no reference in later Assembly law publications through 5 November 2026. This is a partial current-text record, with no reconstructed amendment history. Laws requiring amendment, repeal, text or annex review are not included. Future commencement belongs to the future branch.

| Folder | Law | Commencement |
| --- | --- | --- |
| `lei-15-2026/` | Lei n.º 15/2026: Alteração ao Regulamento do Imposto de Consumo, aprovado pela Lei n.º 4/99/M, de 13 de Dezembro | 2027-09-01 |
| `lei-14-2026/` | Lei n.º 14/2026: Lei de uso das áreas marítimas | 2026-12-01 |
| `lei-13-2026/` | Lei n.º 13/2026: Consolidação dos recursos financeiros do Fundo de Pensões | 2026-08-18 |
| `lei-11-2026/` | Lei n.º 11/2026: Alteração à Lei n.º 11/2000 ‒ Lei Orgânica da Assembleia Legislativa da Região Administrativa Especial de Macau | 2026-10-01 |
| `lei-10-2026/` | Lei n.º 10/2026: Alteração à Lei n.º 5/2011 – Regime de prevenção e controlo do tabagismo | 2027-01-01 |
| `lei-9-2026/` | Lei n.º 9/2026: Alteração à Lei n.º 7/2008 ‒ Lei das relações de trabalho | 2027-01-01 |
| `lei-8-2026/` | Lei n.º 8/2026: Lei da actividade das instituições privadas prestadoras de cuidados de saúde | 2026-12-01 |
| `lei-7-2026/` | Lei n.º 7/2026: Lei da publicidade | 2027-01-01 |
| `lei-6-2026/` | Lei n.º 6/2026: Alteração à Lei n.º 14/2021 ‒ Regime jurídico da construção urbana | 2026-07-01 |
| `lei-4-2026/` | Lei n.º 4/2026: Regime da venda de artigos de ouro e de platina | 2027-01-01 |
| `lei-3-2026/` | Lei n.º 3/2026: Alteração à Lei n.º 4/2010 ‒ Regime da Segurança Social e à Lei n.º 7/2017 ‒ Regime de previdência central não obrigatório | 2026-03-24 |
| `lei-1-2026/` | Lei n.º 1/2026: Alteração à Lei n.º 9/2018 ‒ Criação do Instituto para os Assuntos Municipais | 2026-06-01 |
| `lei-14-2025/` | Lei n.º 14/2025: Alteração à Lei n.º 5/2020 ‒ Salário mínimo para os trabalhadores | 2026-01-01 |
| `lei-12-2025/` | Lei n.º 12/2025: Regime de supervisão e administração de dispositivos médicos | 2026-07-01 |
| `lei-10-2025/` | Lei n.º 10/2025: Lei da contratação pública | 2026-09-01 |
| `lei-9-2025/` | Lei n.º 9/2025: Alteração à Lei n.º 15/2009 – Disposições Fundamentais do Estatuto do Pessoal de Direcção e Chefia | 2025-11-01 |
| `lei-7-2025/` | Lei n.º 7/2025: Alteração à Lei n.º 3/2000 – Da Legislatura e do Estatuto dos Deputados à Assembleia Legislativa | 2025-10-16 |
| `lei-5-2025/` | Lei n.º 5/2025: Lei da actividade das agências de viagens e da profissão de guia turístico | 2026-02-01 |
| `lei-4-2025/` | Lei n.º 4/2025: Lei da actividade de aviação civil | 2026-02-01 |
| `lei-1-2025/` | Lei n.º 1/2025: Alteração à Lei n.º 3/2012 – Quadro geral do pessoal docente das escolas particulares do ensino não superior e à Lei n.º 15/2020 – Estatuto das escolas particulares do ensino não superior | 2025-06-01 |
| `lei-22-2024/` | Lei n.º 22/2024: Regime de gestão dos vendilhões | 2025-03-01 |
| `lei-21-2024/` | Lei n.º 21/2024: Regime jurídico das radiocomunicações | 2025-01-01 |
| `lei-19-2024/` | Lei n.º 19/2024: Alteração ao regime da acção de despejo do Código de Processo Civil | 2025-03-01 |
| `lei-17-2024/` | Lei n.º 17/2024: Alteração à Lei n.º 10/2000 ‒ Lei Orgânica do Comissariado contra a Corrupção da Região Administrativa Especial de Macau | 2024-10-01 |
| `lei-14-2024/` | Lei n.º 14/2024: Regime da transmissão de fracções autónomas de edifícios afectados a habitação económica e habitação intermédia | 2024-09-01 |
| `lei-13-2024/` | Lei n.º 13/2024: Alteração à Lei n.º 2/2020 ‒ Governação electrónica e à Lei n.º 5/2022 ‒ Envio de peças processuais e pagamento de custas por meios electrónicos | 2024-09-01 |
| `lei-10-2024/` | Lei n.º 10/2024: Estabelece as normas fundamentais para a aplicação do Direito da Região Administrativa Especial de Macau nas áreas terrestre e marítima relevantes do lado sudeste do Posto Fronteiriço de Gongbei da Cidade de Zhuhai da Província de Guangdong | 2024-05-28 |
| `lei-9-2024/` | Lei n.º 9/2024: Alteração à Lei n.º 4/1999 ‒ Lei dos juramentos por ocasião do acto de posse | 2024-05-28 |
| `lei-8-2024/` | Lei n.º 8/2024: Alteração à Lei Eleitoral para a Assembleia Legislativa da Região Administrativa Especial de Macau | 2024-04-23 |
| `lei-7-2024/` | Lei n.º 7/2024: Regime jurídico da concessão de crédito para jogos de fortuna ou azar em casino | 2024-08-01 |
| `lei-6-2024/` | Lei n.º 6/2024: Lei sindical | 2025-03-31 |
| `lei-3-2024/` | Lei n.º 3/2024: Regime jurídico da Universidade Politécnica de Macau | 2024-04-01 |
| `lei-16-2023/` | Lei n.º 16/2023: Regime jurídico das empresas de capitais públicos | 2023-11-01 |
| `lei-12-2023/` | Lei n.º 12/2023: Disposições específicas sobre a remuneração do pessoal que exerce funções específicas da Direcção dos Serviços de Educação e de Desenvolvimento da Juventude | 2023-09-01 |
| `lei-9-2023/` | Lei n.º 9/2023: Regime da arbitragem necessária de litígios relativos a infiltrações de água em edifícios | 2023-09-01 |
| `lei-7-2023/` | Lei n.º 7/2023: Regime jurídico de captação de quadros qualificados | 2023-07-01 |
| `lei-2-2023/` | Lei n.º 2/2023: Lei da segurança e saúde ocupacional na construção civil | 2023-11-01 |
| `lei-9-2022/` | Lei n.º 9/2022: Alteração à lista de doenças transmissíveis anexa à Lei n.º 2/2004 - Lei de prevenção, controlo e tratamento de doenças transmissíveis | 2022-07-26 |
| `lei-6-2022/` | Lei n.º 6/2022: Exibição por meios electrónicos dos documentos necessários à condução de veículos | 2022-10-15 |
| `lei-3-2022/` | Lei n.º 3/2022: Alteração à Lei n.º 3/2010 – Proibição de prestação ilegal de alojamento | 2022-04-01 |
| `lei-2-2022/` | Lei n.º 2/2022: Alteração à Lei n.° 9/2006 - Lei de bases do sistema educativo não superior e à Lei n.º 10/2017 - Regime do ensino superior | 2022-06-01 |
| `lei-20-2021/` | Lei n.º 20/2021: Alteração à Lei n.º 3/1999 - Publicação e formulário dos diplomas | 2022-01-01 |
| `lei-9-2021/` | Lei n.º 9/2021: Lei de protecção dos direitos e interesses do consumidor | 2022-01-01 |
| `lei-26-2020/` | Lei n.º 26/2020: Alteração à Lei n.º 9/2002 - Lei de Bases da Segurança Interna da Região Administrativa Especial de Macau | 2021-02-01 |
| `lei-16-2020/` | Lei n.º 16/2020: Lei da actividade de agências de emprego | 2021-03-15 |
| `lei-14-2020/` | Lei n.º 14/2020: Alteração à Lei n.º 5/2006 - Polícia Judiciária | 2020-10-12 |
| `lei-13-2020/` | Lei n.º 13/2020: Alteração à Lei n.º 10/2011 ‒ Lei da habitação económica | 2020-08-18 |
| `lei-12-2020/` | Lei n.º 12/2020: Alteração à Lei n.º 5/2003 - Autorização para a contracção de dívidas pelo Governo da Região Administrativa Especial de Macau | 2020-08-18 |
| `lei-10-2020/` | Lei n.º 10/2020: Alteração à Lei n.º 21/2009 ‒ Lei da contratação de trabalhadores não residentes | 2020-10-05 |
| `lei-7-2020/` | Lei n.º 7/2020: Lei de controlo sanitário animal | 2020-09-01 |
| `lei-4-2020/` | Lei n.º 4/2020: Alteração à Lei n.º 11/2009 – Lei de combate à criminalidade informática | 2020-07-01 |
| `lei-1-2020/` | Lei n.º 1/2020: Estabelece as normas fundamentais para a aplicação do Direito da Região Administrativa Especial de Macau na Zona do Posto Fronteiriço da Parte de Macau do Posto Fronteiriço Hengqin e nas suas zonas contíguas | 2020-03-18 |
| `lei-16-2019/` | Lei n.º 16/2019: Restrições ao fornecimento de sacos de plástico | 2019-11-18 |
| `lei-14-2019/` | Lei n.º 14/2019: Consolidação dos recursos financeiros do Fundo de Segurança Social | 2019-08-13 |
| `lei-11-2019/` | Lei n.º 11/2019: Alteração à Lei n.º 7/2015 ‒ Salário mínimo para os trabalhadores de limpeza e de segurança na actividade de administração predial | 2019-09-01 |
| `lei-9-2019/` | Lei n.º 9/2019: Alteração à Lei n.º 8/2014 – Prevenção e controlo do ruído ambiental | 2019-04-30 |
| `lei-8-2019/` | Lei n.º 8/2019: Regime jurídico de habitação para alojamento temporário e de habitação para troca no âmbito da renovação urbana | 2019-04-24 |
| `lei-7-2019/` | Lei n.º 7/2019: Regime do benefício fiscal para a locação financeira | 2019-04-09 |
| `lei-17-2018/` | Lei n.º 17/2018: Alteração à Lei n.º 10/2012 – Condicionamento da entrada, do trabalho e do jogo nos casinos | 2018-12-28 |
| `lei-16-2018/` | Lei n.º 16/2018: Actualização dos índices mínimos das pensões de aposentação e de sobrevivência | 2019-01-01 |
| `lei-15-2018/` | Lei n.º 15/2018: Revogação do regime jurídico do exercício da actividade 《offshore》 | 2018-12-28 |
| `lei-12-2018/` | Lei n.º 12/2018: Regime jurídico de garantias dos direitos e interesses dos idosos | 2018-11-19 |
| `lei-11-2018/` | Lei n.º 11/2018: Alteração à Lei n.º 2/93/M, de 17 de Maio – Direito de Reunião e de Manifestação | 2018-09-13 |
| `lei-10-2018/` | Lei n.º 10/2018: Benefício fiscal especial para a aquisição de veículos motorizados | 2018-08-14 |

Source: Legislative Assembly of the Macao SAR, official gazette publications. No licence is stated. This selection does not provide all Assembly laws or pre-1999 decree-laws.
