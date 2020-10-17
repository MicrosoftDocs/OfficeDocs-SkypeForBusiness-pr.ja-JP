---
title: 'Lync Server 2013: ユーザーのテレフォニーの構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure telephony for a user
ms:assetid: 4546432e-c839-4517-a2c5-bc0d4d8c6a03
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520988(v=OCS.15)
ms:contentKeyID: 48183987
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 86eade8f7a2ac1db627668ca78b8fb7869e6da71
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520374"
---
# <a name="configure-telephony-for-a-user-in-lync-server-2013"></a>Lync Server 2013 でユーザーのテレフォニーを構成する

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-11-01_

テレフォニーの設定は、ユーザーの Lync Server コントロールパネルで構成できるユーザーアカウントの個別の設定です (つまり、個々のユーザーが Lync Server 2013 に対して有効になっており、組織がテレフォニーをサポートしている場合)。

Lync Server ユーザーテレフォニーオプションは次のとおりです。

  - **音声/ビデオが無効**    ユーザーは、音声とビデオで電話をかけることができません。

  - **Pc 間のみ**    ユーザーは PC 間の音声通話またはビデオ通話のみを行うことができます。

  - **エンタープライズ voip**    ユーザーは、Lync Server 2013 インフラストラクチャを使用して、すべての着信および発信通話をルーティングできます。 また、PC 間の通話も可能です。

  - **リモート通話コントロール**    ユーザーは、Lync Server 2013 を使用してデスクトップ電話を制御でき、PC から PC への通話を行うこともできます。

組織のテレフォニーの構成の詳細については、「展開」のドキュメントの「 [Configure telephony for a lync server 2013](lync-server-2013-configure-telephony-for-a-user.md) 」および「 [lync server 2013 でのエンタープライズ voip の展開](lync-server-2013-deploying-enterprise-voice.md) 」を参照してください。

<div>

## <a name="to-configure-telephony-for-a-specific-user-account"></a>特定のユーザー アカウントのテレフォニーを構成するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで **[ユーザー]** をクリックします。

4.  **[ユーザーの検索]** ボックスに、検索するユーザー アカウントの表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、または回線 URI (Uniform Resource Identifier) の全部または最初の一部を入力して、**[検索]** をクリックします。

5.  表中の変更するユーザー アカウントをクリックします。

6.  [**編集**] メニューの [**変更**] をクリックします。

7.  [**テレフォニー**] で次の操作を行います。
    
      - ユーザーの音声通話およびビデオ通話を無効にするには、**[音声ビデオを無効にする]** をクリックします。
    
      - ユーザーの PC 間の音声通信を有効にするが、リモート通話コントロールやエンタープライズ VoIP は有効にしない場合は、[**PC 間のみ**] をクリックします。 ユーザーが PC 間の音声通信に使用する電話の [**回線 URI**] の値を指定します。
    
      - PC 間の音声通信を含む、サービスポリシーのクラスに従って Lync Server 2010 インフラストラクチャを使用してユーザーの電話をルーティングするには、[ **エンタープライズ voip**] をクリックします。 [**回線 URI**] でエンタープライズ VoIP の電話番号を指定します。 [**ダイヤル プラン ポリシー**] と [**音声ポリシー**] で、ユーザーの適切なポリシーを指定します。 ユーザーのダイヤルした電話番号を E.164 形式に変換するための正規化ルールを指定するには、[**場所のポリシー**] で適切な場所のプロファイルを選択します。
    
      - リモート通話コントロールを有効にするには、ユーザーが Lync Server 2013 のデスクトップ電話回線を制御して、PC 間通話と PC 間通話を行うことができるようにします。そのためには、[ **リモート通話コントロール**] をクリックします。 [**回線 URI**] でリモート通話コントロールの電話番号を指定します。 通話ルーティングを行うには、ユーザーがデスクトップ電話と構内交換機 (PBX) を持っている必要があります。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でユーザーアカウントのプロパティを変更する](lync-server-2013-modifying-user-account-properties.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

