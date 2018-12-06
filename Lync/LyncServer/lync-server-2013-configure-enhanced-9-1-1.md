---
title: 'Lync Server 2013: Enhanced 9-1-1 の構成'
TOCTitle: Enhanced 9-1-1 の構成
ms:assetid: 5967de00-c8b9-4923-86da-6ad3369a4cad
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398390(v=OCS.15)
ms:contentKeyID: 48272196
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での Enhanced 9-1-1 の構成

 

_**トピックの最終更新日:** 2013-02-24_

拡張 9-1-1 (E9-1-1) は、発信者の電話番号を正式な住所または主要道路住所に関連付ける緊急通知機能です。緊急応答機関 (PSAP) はこの情報を使用して、支援を必要とする発信者に緊急サービスをすぐに派遣できます。

E9-1-1 をサポートするために、Lync Server 2013 は場所をクライアントに正確に関連付け、この情報を使用して緊急通話を最も近い PSAP にルーティングできるようにする必要があります。

E9-1-1 展開の計画の詳細については、「[Lync Server 2013 での緊急サービス (E9-1-1) の計画](lync-server-2013-planning-for-emergency-services-e9-1-1.md)」を参照してください。


> [!IMPORTANT]
> Lync Server 2013 がサポートしているのは米国内の E9-1-1 だけです。E9-1-1 を展開するには、認定 E9-1-1 サービス プロバイダーへの SIP 接続を構成するか、公衆交換電話網 (PSTN) ベースの E9-1-1 サービス プロバイダーへの緊急位置識別番号 (ELIN) ゲートウェイを展開する必要があります。詳細については、「<A href="lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md">Lync Server 2013 の Enhanced 9-1-1 (E9-1-1) と仲介サーバー</A>」を参照してください。 トランク接続の構成の詳細については、「<A href="lync-server-2013-configure-a-trunk-with-media-bypass.md">Lync Server 2013 でメディア バイパスを有効にしてトランクを構成する</A>」を参照してください。



## このセクション中

  - [E9-1-1 ボイス ルートの構成](lync-server-2013-configure-an-e9-1-1-voice-route.md)

  - [場所ポリシーの作成](lync-server-2013-create-location-policies.md)

  - [E9-1-1 のサイト情報の構成](lync-server-2013-configure-site-information-for-e9-1-1.md)

  - [場所データベースの構成](lync-server-2013-configure-the-location-database.md)

  - [高度な E9-1-1 機能の構成](lync-server-2013-configure-advanced-e9-1-1-features.md)

