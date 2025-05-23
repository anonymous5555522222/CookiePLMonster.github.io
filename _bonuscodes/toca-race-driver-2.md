---
layout: bonuscodes
title: "TOCA Race Driver 2"
subtitle: "(DTM Race Driver 2, V8 Supercars 2, Race Driver 2006) Bonus Codes"
excerpt: "Cheat Generator for TOCA Race Driver 2/DTM Race Driver 2/V8 Supercars 2/Race Driver 2006."
image: "assets/img/bonuscodes/toca-race-driver-2.jpg"
order: 21
---

{:.disclaimer.info}
On PC, access code generation is broken and on 64-bit systems it always displays an incorrect code `4294967`.
See [Access Code Fix]({% link _games/toca-race-driver/toca-race-driver-2.md %}#access-code-fix){:target="_blank"} for a fix.

{:.disclaimer}
For the Japanese releases, see
[the publisher's website](https://web.archive.org/web/20070506191815fw_/http://www.interchannel.co.jp/game/codemasters/code.html){:target="_blank"}.

<script type="text/python">
from browser import ajax, bind, document, html
import htmlgen
from generators import rd2
from generators.rd2 import ps2

@bind('#cheat-gen-form', 'submit')
def onGenerate(ev):
    data = ajax.form_data(ev.target)

    accessCode = int(data.get('access-code'))
    platform = data.get('platform')
    if ps2.supportsPlatform(platform):
        generateFn = ps2.generateCode
        platformData = None
    else:
        generateFn = rd2.generateCode
        platformData = rd2.getPlatformData(platform)

    numFootnotes = 0
    cheatCodes = ['Unlock championships', 'Unlock bonus championships', 'Double engine power', 'Swap FWD to RWD and vice versa', 'Invincible cars', 'Unlock cutscenes']
    if platform == 'psp':
        cheatCodes.append('Unlock all Trans World Cup events' + htmlgen.newElement(document['footnote-sup'], id='rd2006-only', notenum=1, num=0))
        numFootnotes += 1

    outputBlock = document['output-window']
    outputs = outputBlock.select_one('output')
    outputBlock.style.display = 'block'
    outputs.clear()

    outputFootnotesBlock = document['output-footnotes']
    outputFootnotes = outputFootnotesBlock.select_one('output')
    outputFootnotesBlock.style.display = 'block'
    outputFootnotes.clear()
    if numFootnotes > 0:
        outputFootnotes <= html.OL(htmlgen.newElement(document['footnote-template'], id='rd2006-only', num=1, note='Race Driver 2006 only.'))

    def gen():
        for index, cheat in enumerate(cheatCodes):
            cryptedCode = generateFn(platformData, accessCode, index)
            if cryptedCode:
                yield cheat, cryptedCode
    outputs <= html.DL(html.DIV(html.DT(term + ':') + ' ' + html.DD(code)) for term, code in gen())

document['access-code'].min = 1
document['access-code'].max = rd2.ACCESS_CODE_MAX

platformSelect = document['platform-select']
platformSelect.style.display = 'inline'
platformSelect.select_one('select') <= (html.OPTION(n, value=i) for n, i in [('PC', 'pc'), ('PS2', 'ps2'), ('PSP', 'psp'), ('Xbox', 'xbox')])
</script>
