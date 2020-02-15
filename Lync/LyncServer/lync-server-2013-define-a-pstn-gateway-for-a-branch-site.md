---
title: 'Lync Server 2013: ブランチサイト用の PSTN ゲートウェイの定義'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a PSTN gateway for a branch site
ms:assetid: 87be2fe2-1d56-4062-b430-439d4536414c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398689(v=OCS.15)
ms:contentKeyID: 48184724
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ae74ead7eb481a6551156fc0ce228c743fdf1b6
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043669"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-pstn-gateway-for-a-branch-site-in-lync-server-2013"></a>Lync Server 2013 でのブランチサイト用の PSTN ゲートウェイの定義

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-21_

この手順は、少なくとも1つのフロントエンドプールまたは Standard Edition サーバーが含まれるセントラルサイトで実行してください。

<div>


> [!IMPORTANT]  
> 手順を実行する前に、以下の条件が整っている必要があります。 
> <UL>
> <LI>
> <P>Lync Server 2013&nbsp;通信ソフトウェアは、セントラルサイトで設定する必要があります。</P>
> <LI>
> <P>中央サイトに仲介サーバーを展開する必要があります。</P></LI></UL>



</div>

<div>

## <a name="to-define-a-pstn-gateway"></a>PSTN ゲートウェイを定義するには

1.  [**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server**]、[**Lync Server トポロジ ビルダー**] の順にクリックします。

2.  コンソール ツリーで中央サイトを展開して、[**ブランチ オフィス サイト**] を展開し、公衆交換電話網 (PSTN) ゲートウェイを定義するブランチ サイトの名前を展開し、次に [**共有コンポーネント**] を展開します。

3.  [**PSTN ゲートウェイ**] を右クリックして、[**新しい IP/PSTN ゲートウェイ**] をクリックします。

4.  [**新しい IP/PSTN ゲートウェイの定義**] ダイアログ ボックスで、[**ゲートウェイ FQDN または IP アドレス**] をクリックして、ブランチ サイトに展開するゲートウェイの完全修飾ドメイン名 (FQDN) または IP アドレスを入力します。

5.  [**IP/PSTN ゲートウェイのリッスン ポート**] をクリックして、既定値をそのまま使用します。

6.  [**SIP トランスポート プロトコル**] リストで、ゲートウェイで使用するトランスポート プロトコルをクリックして、[**OK**] をクリックします。
    
    <div>
    

    > [!NOTE]  
    > セキュリティ上の理由のため、トランスポート層セキュリティ (TLS) をサポートする PSTN ゲートウェイの使用を強くお勧めします。

    
    </div>

<div>


> [!TIP]  
> コマンドレット <STRONG>Set-CsPstnGateway</STRONG> を使用して、PSTN ゲートウェイのプロパティを変更します。 詳細については、「Lync Server 管理シェルのヘルプ」の「 <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsPstnGateway">Set-CsPstnGateway</A>」を参照してください。



</div>

ブランチサイトの復元の**次のステップ**: [Lync Server 2013 でのブランチサイトの復元のユーザーの構成](lync-server-2013-configuring-users-for-branch-site-resiliency.md)

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 の PSTN ゲートウェイの展開オプション](lync-server-2013-pstn-gateway-deployment-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

