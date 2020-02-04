---
title: 'Lync Server 2013: ユーザーのテレフォニーを構成する'
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
ms.openlocfilehash: d57c4799c0fe9bb9dc698c3e0e74a9d73cbde524
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740007"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-telephony-for-a-user-in-lync-server-2013"></a>Lync Server 2013 でユーザーのテレフォニーを構成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-11-01_

[テレフォニー設定] は、ユーザーの Lync Server コントロールパネルで構成できるユーザーアカウントの個々の設定の一部です (つまり、個々のユーザーが Lync Server 2013 に対して有効になっていて、組織がテレフォニーをサポートしている場合)。

Lync Server のユーザーテレフォニーオプションには、次のようなものがあります。

  - **音声/ビデオを無効**   にすると、ユーザーは音声とビデオを使って通話を発信できなくなります。

  - ****   Pc 間の音声通話またはビデオ通話は、ユーザーのみが実行できます。

  - **エンタープライズ voip**   ユーザーは、Lync Server 2013 インフラストラクチャを使用して、すべての着信通話と発信通話をルーティングすることができます。 ユーザーは PC 間の通話を発信することもできます。

  - **リモート通話コントロール**   ユーザーは Lync Server 2013 を使ってデスクトップ電話を制御できます。また、pc 間通話もできます。

組織のテレフォニーの構成の詳細については、展開ドキュメントの「lync server [2013 でユーザーのテレフォニーを構成する](lync-server-2013-configure-telephony-for-a-user.md)」および「[エンタープライズ Voip を lync Server 2013 で展開](lync-server-2013-deploying-enterprise-voice.md)する」を参照してください。

<div>

## <a name="to-configure-telephony-for-a-specific-user-account"></a>特定のユーザーアカウントのテレフォニーを構成するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーション バーで [**ユーザー**] をクリックします。

4.  [**ユーザーの検索**] ボックスに、表示名、名、姓、セキュリティアカウントマネージャー (SAM) アカウント名、SIP アドレス、または必要なユーザーアカウントの行の Uniform resource IDENTIFIER (URI) の最初の部分を入力し、[**検索**] をクリックします。

5.  表で、変更するユーザーアカウントをクリックします。

6.  [**編集**] メニューの [**変更**] をクリックします。

7.  [**テレフォニー**] で、次の操作を行います。
    
      - ユーザーの音声通話とビデオ通話を無効にするには、[**オーディオ/ビデオを無効**にする] をクリックします。
    
      - ユーザーに対して PC 間音声通信を有効にしますが、リモート通話コントロールまたはエンタープライズボイスでは使用できないようにするには、[ **pc 間のみ**] をクリックします。 ユーザーが PC 間の音声通信に使用する電話の**ライン URI**の値を指定します。
    
      - PC 間の音声通信など、サービスポリシーのクラスに従って Lync Server 2010 インフラストラクチャを使用して、ユーザーの電話をルーティングするには、[**エンタープライズ voip**] をクリックします。 [**行の URI**] で、エンタープライズ voip の電話番号を指定します。 [**ダイヤルプランポリシー** ] と [**ボイスポリシー**] で、ユーザーに適したポリシーを指定します。 ユーザーがダイヤルした電話番号を E-164 形式で翻訳するための正規化ルールを指定するには、**場所のポリシー**で適切な場所のプロファイルを選択します。
    
      - ユーザーが Lync Server 2013 からデスクトップ電話回線を制御できるようにするリモート通話コントロールを有効にするには、[**リモート通話コントロール**] をクリックします。 [**行の URI**] で、リモート通話コントロール用の電話番号を指定します。 ユーザーは、通話ルーティング用に、デスクトップ電話と構内交換機 (PBX) 接続を持っている必要があります。

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

