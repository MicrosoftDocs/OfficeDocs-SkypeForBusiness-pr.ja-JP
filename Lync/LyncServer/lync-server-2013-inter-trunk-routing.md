---
title: 'Lync Server 2013: トランク間ルーティング'
TOCTitle: トランク間ルーティング
ms:assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ721940(v=OCS.15)
ms:contentKeyID: 49887222
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのトランク間ルーティング

 

_**トピックの最終更新日:** 2012-10-08_

Lync Server 2013 は、トランク間ルーティングのサポートを通して基本的なセッション管理を提供します。この新しい機能により、Lync Server では、通話コントロール機能をダウンストリーム テレフォニー システムに提供できます。トランク間ルーティングは IP-PBX と公衆交換電話網 (PSTN) ゲートウェイを相互に接続でき、それによって、構内交換機 (PBX) 電話機からの通話を PSTN にルーティングしたり、着信した PSTN の通話を PBX 電話機にルーティングしたりできます。同様に、Lync Server は複数の IP-PBX システムを相互に接続でき、それによって、異なる IP-PBX システムの PBX 電話機の間で通話を発信および受信できます。

次の図では、PSTN ゲートウェイと IP-PBX の間の相互接続を提供する Lync Server 2013 を示します。

![Lync Server、PSTN ゲートウェイ/IP-PBX の接続図](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Lync Server、PSTN ゲートウェイ/IP-PBX の接続図")

次の図では、2 つの IP-PBX システム間を接続する Lync Server 2013 を示します。

![Lync Server、IP-PAX システムの相互接続図](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Lync Server、IP-PAX システムの相互接続図")

