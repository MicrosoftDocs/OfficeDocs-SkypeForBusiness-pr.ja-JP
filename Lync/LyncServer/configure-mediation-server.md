---
title: 仲介サーバーの構成
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Configure Mediation Server
ms:assetid: 583236fd-33cd-4045-81df-baa58ed07779
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204913(v=OCS.15)
ms:contentKeyID: 48184207
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 389c6e5c017594bf386109541a379bd5ae2f7e01
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006653"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-mediation-server"></a>仲介サーバーの構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-28_

この手順では、従来の Office Communications Server 2007 R2 仲介サーバーではなく、lync server 2013 仲介サーバーを使用するように Lync Server 2013 プールを構成する手順について説明します。

サーバーの役割を追加または削除する際に、トポロジを正常に公開したり、有効または無効にするには、RTCUniversalServerAdmins グループおよび Domain Admins グループのメンバーであるユーザーとしてログインしている必要があります。サーバーの役割を追加するための適切な管理者権限およびアクセス許可を委任することもできます。詳細については、Standard Edition サーバーまたは Enterprise Edition サーバーの「展開」のドキュメントの「セットアップのアクセス許可の委任」を参照してください。他の構成変更の場合は、RTCUniversalServerAdmins グループのメンバーシップのみが必要です。

<div>


> [!NOTE]  
> Lync Server 2013 で動作する、認定 PSTN ゲートウェイ、IP-PBX、および SIP トランキングサービスの検索に関する最新情報については、「Microsoft ユニファイドコミュニケーションオープン<A href="http://go.microsoft.com/fwlink/p/?linkid=206015">http://go.microsoft.com/fwlink/p/?linkId=206015</A>相互運用性プログラム」 () を参照してください。



</div>

<div>

## <a name="to-configure-mediation-server-using-topology-builder"></a>トポロジ ビルダーを使用して仲介サーバーを構成するには

1.  トポロジ ビルダーで既存のトポロジを開きます。

2.  左ウィンドウで、[**PSTN ゲートウェイ**] に移動します。

3.  [**PSTN ゲートウェイ**] を右クリックし、[**新しい IP/PSTN ゲートウェイ**] をクリックします。

4.  [**新しい IP/PSTN ゲートウェイの定義**] ページに、次の情報を入力します。
    
      - ゲートウェイの FQDN または IP アドレスを入力します。ゲートウェイが TLS プロトコルを使用する場合は、ゲートウェイの FQDN が必要です。
    
      - [**IP/PSTN ゲートウェイのリッスン ポート**] の既定値をそのまま使用するか、変更されている場合は新しいリッスン ポートを入力します。
    
      - [**SIP 転送プロトコル**] を設定します。

5.  左ウィンドウで、[**Enterprise Edition フロント エンド プール**] または [**Standard Edition サーバー**] に移動します。

6.  プールを右クリックし、[**プロパティの編集**] をクリックします。

7.  [**仲介サーバー**] で、[**リッスン ポート**] を設定します。

8.  次に、新しく作成した PSTN ゲートウェイを関連付けます。それには、PSTN ゲートウェイを選択し、[**追加**] をクリックします。

9.  **トポロジ ビルダー**で、最上位ノードの [**Lync Server**] を選択します。

10. [**操作**] メニューの [**トポロジの公開**] を選択し、[**次へ**] をクリックします。

11. **公開ウィザード**の実行が完了したら、[**完了**] をクリックしてウィザードを閉じます。

<div>


> [!NOTE]  
> 次のトピック「<A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">新しい Lync server 2013 仲介サーバーを使用するように音声ルートを変更</A>する」を完了して、音声ルートが正しい仲介サーバーを指していることを確認することが重要です。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

