import discord
import os


intents = discord.Intents.default()
intents.message_content = True
client = discord.Client(intents=intents)

@client.event
async def on_ready():
    print(f'{client.user}kayarak giriş yaptı')
@client.event
async def on_message(message):
    if message.author == client.user:
        return
    if message.content.startswith('$Merhaba'):
        await message.channel.send("Merhaba programa hoş geldin! Konu: Çevre kirliliği")
    elif message.content.startswith('$Çevre kirliliği nedir'):
        await message.channel.send("Çevre kirliliği, çevrenin doğal olmayan bir şekilde insan eliyle doğallığının bozulmasıdır. Bu ekosistemi bozma eylemleri; kirlenme şeklinde tabir edilmektedir. Çevre; dünya üzerinde yaşamını sürdüren canlılarının hayatları boyunca ilişkilerini sürdürdüğü dış ortamdır.")
    elif message.content.startswith('$Nasıl engelleriz'):
        await message.channel.send("Atıklarınızı ayrıştırın, geri dönüşüme katkı sağlayın.")
    elif message.content.startswith("$fotoğraf"):
        with open("resim/cevre.jpg", "rb") as cevrefoto:
            resim = discord.File(cevrefoto)
        await message.channel.send(file=resim)
    elif message.content.startswith('$Uzun hali'):
        await message.channel.send("Çevrenin canlı ögelerinin hayat aktivitelerini olumsuz yönde etkileyen, cansız ögelerin üzerinde ise yapısal zararlar meydana getiren ve niteliklerini bozan yabancı maddelerin hava, su ve toprağa yoğun bir şekilde karışması olayına çevre kirliliği denir. Hızla artan insan nüfusu ihtiyaçları arttırmakta, insan eliyle yaratılan kirliliğin tabiata ve çevreye verdiği zararın boyutu her geçen gün artmaktadır. Yaşamı daha mükemmel bir hale getirmek, daha sağlıklı ve uzun bir ömür sağlayabilmek amacına dönük bazı gelişmelerin, kırsal ve kentsel alanlarda doğal kaynaklarını bozduğu, su, hava, toprak kirlenmesine yol açtığı, bitki ve hayvan varlığına ve sağlığına zarar verdiği açıkça görülebilen bir gerçek haline gelmiştir.")
    elif message.content.startswith('$Zararları'):
        await message.channel.send("Küresel ısınma gibi iklim değişiklikleri,Erozyon ile verimli toprağın yani besin kaynaklarının kaybolması,Su kaynaklarının tükenmesi,Enerji kıtlığı - yiyecek kıtlığı,Canlıların nesillerinin tükenmesi sonucu biyolojik çeşitliliğin azalması")
    elif message.content.startswith('$Çevre kirliliğinin sorunları'):
        await message.channel.send("İklim değişikliği, çölleşme, biyolojik çeşitlilik kaybı, ormansızlaşma, ozon tabakasının tahribatı, hava, su ve toprak kirliliği, tehlikeli ve plastik atıklar, deniz ve okyanus kirliliği gibi çevre sorunları sürdürülebilir kalkınmayı tehlikeye atmakta; insanların güvenliği, sağlığı ve üretkenliği")
    elif message.content.startswith('$Nerelerde çevre kirliliği olur'):
        await message.channel.send("Konutlar, endüstri kuruluşları, termik santraller, gübreler, kimyasal mücadele ilaçları (pestisitler), sanayi atık suları")
    else:
        await message.channel.send(message.content)

client.run("MTE1ODgxNDQwODE1MjE5OTE2OA.GflZ7S.UGmuVMPhzo3t3n6nmGL23hielxILoenbLaaBQQ")
