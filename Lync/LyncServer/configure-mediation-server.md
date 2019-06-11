---
title: 仲介サーバーを構成する
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Configure Mediation Server
ms:assetid: 583236fd-33cd-4045-81df-baa58ed07779
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204913(v=OCS.15)
ms:contentKeyID: 48184207
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60bacd308249536aee49101cbcab739a0876343e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840826"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-mediation-server"></a>仲介サーバーを構成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-28_

この手順では、従来の Office Communications Server 2007 R2 仲介サーバーではなく、lync server 2013 仲介サーバーを使用するように Lync Server 2013 プールを構成する手順について説明します。

トポロジを正常に発行、有効化、または無効にするには、RTCUniversalServerAdmins および Domain Admins グループのメンバーであるユーザーとしてログインしている必要があります。 また、サーバーの役割を追加するための適切な管理者権限と権限を委任することもできます。 詳細については、「Standard Edition server または Enterprise Edition server 展開ドキュメントの委任セットアップの権限」を参照してください。 その他の構成変更については、RTCUniversalServerAdmins グループのメンバーシップのみが必要です。

<div>


> [!NOTE]  
> Lync Server 2013 で動作する、限定 PSTN ゲートウェイ、IP Pbx、SIP トランクサービスの検索に関する最新情報については、「Microsoft ユニファイド通信で<A href="http://go.microsoft.com/fwlink/p/?linkid=206015">http://go.microsoft.com/fwlink/p/?linkId=206015</A>の相互運用プログラムのオープン」を参照してください。



</div>

<div>

## <a name="to-configure-mediation-server-using-topology-builder"></a>トポロジビルダーを使用して仲介サーバーを構成するには

1.  トポロジビルダーから既存のトポロジを開きます。

2.  左側のウィンドウで、[ **PSTN ゲートウェイ**] に移動します。

3.  [ **PSTN ゲートウェイ**] を右クリックし、[**新しい IP/PSTN ゲートウェイ**] をクリックします。

4.  [**新しい IP/PSTN ゲートウェイの定義**] ページに次の情報を入力します。
    
      - ゲートウェイの FQDN または IP アドレスを入力します。 ゲートウェイで TLS プロトコルを使用している場合は、ゲートウェイの FQDN が必要です。
    
      - **IP/PSTN ゲートウェイのリスニングポート**の既定値をそのまま使うか、変更された場合は新しいリッスンポートを入力します。
    
      - **Sip トランスポートプロトコル**を設定します。

5.  左側のウィンドウで、 **Enterprise Edition のフロントエンドプール**または**Standard Edition サーバー**に移動します。

6.  プールを右クリックし、[プロパティの**編集**] をクリックします。

7.  [**仲介サーバー**] で、**リッスンポート**を設定します。

8.  次に、新しく作成した PSTN ゲートウェイを選択して [**追加**] をクリックします。

9.  [**トポロジビルダー**] で、トップノードの**Lync Server**を選択します。

10. [**アクション**] メニューで、[**発行トポロジ**] を選択し、[**次へ**] をクリックします。

11. **発行ウィザード**が完了したら、[**完了**] をクリックしてウィザードを閉じます。

<div>


> [!NOTE]  
> 次のトピック「ボイスルートを変更して、<A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">新しい Lync server 2013 仲介サーバーを使用する</A>」を実行し、ボイスルーティングが正しい仲介サーバーをポイントするようにすることが重要です。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

