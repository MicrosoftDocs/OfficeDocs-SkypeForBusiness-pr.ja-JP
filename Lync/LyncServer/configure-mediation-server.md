---
title: 仲介サーバーを構成します。
TOCTitle: Configure Mediation Server
ms:assetid: 583236fd-33cd-4045-81df-baa58ed07779
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204913(v=OCS.15)
ms:contentKeyID: 48184207
ms.date: 07/23/2014
mtps_version: v=OCS.15
ms.openlocfilehash: 143d98cebc151473b790246bc78d75e6e2f4185a
ms.sourcegitcommit: a599bdd5057c4fc38e14b4f14961e1a6bf08ee8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/05/2018
ms.locfileid: "27128170"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-mediation-server"></a>仲介サーバーを構成します。

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックは最終更新日:** 2012-09-28_

この手順では、Lync Server 2013 の仲介サーバーを使用して、レガシ Office 通信サーバー 2007 R2 仲介サーバーではなく、Lync Server 2013 プールを構成する手順について説明します。

正常に発行を有効にするなどを追加するか、サーバーの役割を削除すると、トポロジを無効にする、RTCUniversalServerAdmins グループおよび Domain Admins グループのメンバーであるユーザーとしてに記録される必要があります。 適切な管理者権限およびサーバーの役割を追加するためのアクセス許可を委任することもできます。 詳細については、Standard Edition サーバーまたは Enterprise Edition サーバーの展開に関するドキュメントのアクセス許可の委任の設定を参照してください。 その他の構成の変更、RTCUniversalServerAdmins グループのメンバーシップのみが必要です。

<div>


> [!NOTE]  
> 修飾の PSTN ゲートウェイ、IP Pbx には、Lync Server 2013 を使用する SIP トランキング サービスを探すことに最新の情報を参照してくださいマイクロソフト ユニファイド コミュニケーション オープン相互運用性プログラム」に<A href="http://go.microsoft.com/fwlink/p/?linkid=206015">http://go.microsoft.com/fwlink/p/?linkId=206015</A>。



</div>

<div>

## <a name="to-configure-mediation-server-using-topology-builder"></a>仲介サーバーを使用するトポロジのビルダーを構成するのには

1.  トポロジ ビルダーでは、既存のトポロジを開きます。

2.  左側のウィンドウでは、 **PSTN ゲートウェイ**に移動します。

3.  **PSTN ゲートウェイ**を右クリックし、**新規の IP ネットワーク アドレス**] をクリックします。

4.  次の情報が**新しい IP または PSTN ゲートウェイの定義**] ページを完了します。
    
      - ゲートウェイの FQDN または IP アドレスを入力します。 ゲートウェイが TLS プロトコルを使用している場合、ゲートウェイの FQDN が必要です。
    
      - **IP ネットワーク アドレスのリッスンするポート**の既定値を受け入れるか、変更された場合は、新しいリッスン ポートを入力します。
    
      - の**Sip トランスポート プロトコル**を設定します。

5.  左側のウィンドウでは、**エンタープライズ エディションのフロント エンド プール**または**Standard Edition Server**に移動します。

6.  プールを右クリックし、 **[プロパティの編集**] をクリックします。

7.  **仲介サーバー**] の下には、**リッスンするポート**を設定します。

8.  次を選択し、[**追加**] をクリックして新しく作成した PSTN ゲートウェイを関連付けます。

9.  **トポロジ ビルダー**では、 **Lync Server**の最上位ノードを選択します。

10. **[操作**] メニューから**公開トポロジ**を選択し、[**次へ**] をクリックします。

11. **発行ウィザード**を完了すると、ウィザードを終了するのには**完了**ををクリックします。

<div>


> [!NOTE]  
> 次のトピックでは、ボイス ルートは、適切な仲介サーバーを指していることを確認するのには<A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">新しい Lync Server 2013 の仲介サーバーを使用するボイス ルートの変更</A>を完了することが重要です。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

