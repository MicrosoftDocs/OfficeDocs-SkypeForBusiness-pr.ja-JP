---
title: 'Lync Server 2013: トランク間ルーティング'
TOCTitle: トランク間ルーティング
ms:assetid: d3a33b4a-8bf4-4a8c-a371-8ef79e740780
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205272(v=OCS.15)
ms:contentKeyID: 48273673
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 のトランク間ルーティング

 

_**トピックの最終更新日:** 2012-10-20_

Lync Server 2013 は IP-PBX と公衆交換電話網 (PSTN) ゲートウェイを相互に接続でき、それによって、PBX 電話機からの通話を PSTN にルーティングしたり、着信した PSTN の通話を構内交換機 (PBX) 電話機にルーティングしたりできます。同様に、 Lync Server 2013 は複数の IP-PBX システムを相互に接続でき、それによって、異なる IP-PBX システムの PBX 電話機の間で通話を発信および受信できるようになります。

このトランク間ルーティング機能は、 Lync Server 管理シェル コマンドレット **Set-CsTrunkConfiguration** の新しいパラメーター PstnUsages を使用して構成できます。このパラメーターでは、使用する一連の PSTN 使用法レコードを指定します。トランクはこの PSTN 使用法を使用して、ルートを決定し、それに従って着信したすべての通話をルーティングします。

    Set-CsTrunkConfiguration -Identity <TrunkId> -PstnUsages @{add="<UsageString>"}

次の図では、PSTN ゲートウェイと IP-PBX の間の相互接続を提供する Lync Server 2013 を示します。

**ゲートウェイと IP PBX の間のトランク間ルーティング**

![Lync Server、PSTN ゲートウェイ/IP-PBX の接続図](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Lync Server、PSTN ゲートウェイ/IP-PBX の接続図")

次の図では、2 つの IP-PBX システム間を相互接続する Lync Server 2013 を示します。

**2 つの IP PBX 間のトランク間ルーティング**

![Lync Server、IP-PAX システムの相互接続図](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Lync Server、IP-PAX システムの相互接続図")

