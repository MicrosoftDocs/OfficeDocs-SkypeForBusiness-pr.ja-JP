---
title: 'Lync Server 2013: 発信者番号通知のプレゼンテーション'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Caller ID presentation
ms:assetid: 6a643961-a0a1-41d1-96ba-6c428a89d82e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204980(v=OCS.15)
ms:contentKeyID: 48184425
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 016913ad68865f7d93512cc7383f2cfb47497ebe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840694"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="caller-id-presentation-in-lync-server-2013"></a>Lync Server 2013 での発信者番号通知のプレゼンテーション

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-22_

Lync Server 2010 を使用すると、通話先の国の電話番号 (電話番号) を、トランクのピアによって要求されるローカルのダイヤル形式 (関連付けられているゲートウェイ、構内交換機 (PBX)、SIP トランクなど) に変換することができます。 これを行うためには、トランク ピアへのルーティングの前に要求 URI を変換する変換ルールを 1 つ以上定義する必要があります。

Lync Server 2013 では、発信者の電話番号 (つまり、発信者が発信している電話番号) を、樹幹形式から、トランクピアによって要求されるローカルのダイヤル形式に翻訳するオプションも導入されています。 たとえば、ダイヤル文字列の冒頭から +44 を取り除いて 0114 に置き換える変換ルールを記述できます。

<div id="sectionSection0" class="section">

**Lync Server コントロールパネルを使用して発信者番号認識を構成するには**

1.  RTCUniversalServerAdmins グループのメンバーとして、あるいは CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。 詳細については、「 [Lync Server 2013 でセットアップのアクセス許可を委任](lync-server-2013-delegate-setup-permissions.md)する」を参照してください。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーション バーで [**音声ルーティング**] をクリックし、[**トランク構成**] をクリックします。

4.  [**トランク構成**] ページで、既存のトランク (たとえば [**グローバル**] トランク) をダブルクリックして [**編集トランク構成**] ダイアログ ボックスを表示します。

5.  発信者番号のプレゼンテーションを構成するには、次のようにします。
    
      - エンタープライズ Voip 展開で利用できるすべての翻訳ルールの一覧から1つ以上のルールを選択するには、[**選択**] をクリックします。 [**発信者番号の変換ルール**] で、トランクに関連付けるルールをクリックし、[**OK**] をクリックします。
    
      - 新しい変換ルールを定義してトランクに関連付ける場合は、[**新規**] をクリックします。 新しいルールの定義の詳細については、展開ドキュメントの「 [Lync Server 2013 で翻訳ルールを定義](lync-server-2013-defining-translation-rules.md)する」を参照してください。
    
      - 既にトランクに関連付けられている変換ルールを編集するには、ルールの名前をクリックして、[**詳細の表示**] をクリックします。 詳細については、展開ドキュメントの「 [Lync Server 2013 で翻訳ルールを定義](lync-server-2013-defining-translation-rules.md)する」を参照してください。
    
      - 既存の変換ルールをコピーしてそれを基に新しいルールを定義するには、ルールの名前をクリックして [**コピー**] をクリックし、[**貼り付け**] をクリックします。 詳細については、「 [Lync Server 2013 で翻訳ルールを定義](lync-server-2013-defining-translation-rules.md)する」を参照してください。
    
      - トランクから変換ルールを削除するには、ルールの名前を選択状態にして、[**削除**] をクリックします。
    
    <div>
    

    > [!WARNING]  
    > 関連付けられたトランク ピアに対して変換ルールを構成している場合は、2 つのルールが競合する危険があるため、変換ルールをトランクに関連付けないでください。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

