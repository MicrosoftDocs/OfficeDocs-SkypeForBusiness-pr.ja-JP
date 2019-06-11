---
title: 'Lync Server 2013: ブランチ サイト用の PSTN ゲートウェイの定義'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Define a PSTN gateway for a branch site
ms:assetid: 87be2fe2-1d56-4062-b430-439d4536414c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398689(v=OCS.15)
ms:contentKeyID: 48184724
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c253f82001fef4dd52e19dccb11e7ac77bb12417
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833717"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-pstn-gateway-for-a-branch-site-in-lync-server-2013"></a>Lync Server 2013 でのブランチ サイト用の PSTN ゲートウェイの定義

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-21_

この手順はセントラルサイトで実行します。これには、少なくとも1つのフロントエンドプールまたは Standard Edition サーバーが含まれます。

<div>


> [!IMPORTANT]  
> この手順を実行する前に、次の条件を満たしている必要があります。 
> <UL>
> <LI>
> <P>Lync Server 2013&nbsp;通信ソフトウェアがセントラルサイトでセットアップされている必要があります。</P>
> <LI>
> <P>仲介サーバーがセントラルサイトに展開されている必要があります。</P></LI></UL>



</div>

<div>

## <a name="to-define-a-pstn-gateway"></a>PSTN ゲートウェイを定義するには

1.  [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server**]、[ **lync server Topology Builder**] の順にクリックします。

2.  コンソールツリーで、[セントラルサイト]、[**ブランチオフィスサイト**] の順に展開し、公衆交換電話網 (PSTN) ゲートウェイを定義するブランチサイトの名前を展開して、[**共有コンポーネント**] を展開します。

3.  [ **PSTN ゲートウェイ**] を右クリックし、[**新しい IP/PSTN ゲートウェイ**] をクリックします。

4.  [**新しい IP/PSTN ゲートウェイの定義**] ダイアログボックスで、[**ゲートウェイの FQDN または ip アドレス**] をクリックし、ブランチサイトで展開するゲートウェイの完全修飾ドメイン名 (FQDN) または ip アドレスを入力します。

5.  [ **IP/PSTN ゲートウェイのリスニングポート**] をクリックし、既定値をそのまま使用します。

6.  [ **SIP トランスポートプロトコル**] ボックスの一覧で、ゲートウェイが使用するトランスポートプロトコルをクリックし、[ **OK]** をクリックします。
    
    <div>
    

    > [!NOTE]  
    > セキュリティ上の理由から、トランスポート層セキュリティ (TLS) をサポートする PSTN ゲートウェイを使用することを強くお勧めします。

    
    </div>

<div>


> [!TIP]  
> コマンドレットを<STRONG></STRONG>使用して、PSTN ゲートウェイのプロパティを変更します。 詳しくは、「Lync Server 管理シェルのヘルプ」の「 <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsPstnGateway">Set-CsPstnGateway</A>」をご覧ください。



</div>

ブランチサイトの回復の**次のステップ**: [Lync Server 2013 でブランチサイトの回復用ユーザーを構成する](lync-server-2013-configuring-users-for-branch-site-resiliency.md)

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

