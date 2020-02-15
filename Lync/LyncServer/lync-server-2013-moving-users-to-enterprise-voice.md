---
title: 'Lync Server 2013: エンタープライズ Voip へのユーザーの移動'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Moving users to Enterprise Voice
ms:assetid: a2df6d51-5cf2-4d3e-8f97-496af5fd5e5e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412758(v=OCS.15)
ms:contentKeyID: 48184958
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b0320cb10e4122e5f5c42a659ad8de54ce3ae5b6
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42039161"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="moving-users-to-enterprise-voice-in-lync-server-2013"></a>Lync Server 2013 でのエンタープライズ Voip へのユーザーの移動

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-18_

既存の PBX テレフォニーインフラストラクチャからエンタープライズ Voip にユーザーを移動する場合、展開プロセスには、「 [Lync Server 2013 でのエンタープライズ voip の計画](lync-server-2013-planning-for-enterprise-voice.md)」で説明されている計画プロセスの一部ではないいくつかの手順が含まれています。 以前に展開したエンタープライズ VoIP からのユーザー移行の詳細については、インストール メディアに含まれている「移行」のドキュメントを参照してください。

既存のテレフォニー インフラストラクチャからエンタープライズ VoIP にユーザーを移動するプロセスは、次のステップで構成されます。

1.  主要電話番号を指定します。

2.  エンタープライズ VoIP に対してユーザーを有効化します。

3.  ユーザー向けのダイヤル プランを準備します。

4.  ユーザーの音声ポリシーを計画します。

5.  通話ルートを計画します。

6.  エンタープライズ VoIP に対して有効化されたユーザーの通話を再ルーティングするように PBX または SIP トランクを構成します。

7.  ユーザーを Exchange ユニファイドメッセージング (UM) に移動します (推奨)。

このトピックでは、これらの各ステップに必要な計画について説明します。

<div>

## <a name="step-1-designate-primary-phone-numbers"></a>ステップ 1. 主要電話番号を指定する

エンタープライズ VoIP により、音声と他のメッセージング メディアが統合されます。着信通話がサーバーに到着すると、サーバーはその番号をユーザーの SIP URI にマッピングし、該当の SIP URI に関連付けられたすべてのクライアント エンドポイントに通話を分岐させます。このプロセスでは、各ユーザーが主要電話番号に関連付けられていることが必要になります。

主要電話番号の要件は次のとおりです。

  - グローバルに一意であること。内線番号の場合は企業内で一意であること。

  - 企業が所有し、企業内でルーティングできること。個人用の番号を使用することはできません。

エンタープライズユーザーは、Active Directory ドメインサービスに2つ以上の電話番号を表示することができます。 特定のユーザーに関連付けられたすべての電話番号は、Active Directory ユーザーとコンピューターのスナップインで、そのユーザーのプロパティ シートを使用して表示または変更できます。

**[ユーザーのプロパティ]** ダイアログ ボックスの **[全般]** タブの **[電話番号]** ボックスには、ユーザーの主要な勤務先番号が表示されています。通常、この番号がユーザーの主要電話番号として指定されます。

一部のユーザーが特殊な要件を持つ場合がありますが (すべての着信通話を管理スタッフ経由でルーティングすることを希望する役員など)、このような例外はその必要性が明確かつ重要であるものだけに限定する必要があります。

主要電話番号を選択したら、その番号に対して次の処理を行う必要があります。

  - 可能な限り、E.164 形式に正規化します。

  - Active Directory の **msRTCSIP-line** 属性にコピーします。
    
    <div>
    

    > [!NOTE]  
    > <STRONG>リモート通話コントロール (RCC) との共存</STRONG><BR>RCC は、Lync Server を使用して、デスクトップ PBX 電話を監視および制御する機能です。 コントロールは、PBX へのゲートウェイとして機能するサーバー経由でルーティングされます。 RCC と エンタープライズ VoIP の両方に対してユーザーを構成することはできませんが、どちらの場合も、回線 URI 設定はユーザーの主要電話番号を指定します。<BR>既に PBX インフラストラクチャが存在し、一部のユーザーに引き続き使用させたい場合は、徐々にエンタープライズ VoIP を組織へ導入することができます。 この展開シナリオの詳細については、「計画」のドキュメントの「 <A href="lync-server-2013-direct-sip-deployment-options.md">DIRECT SIP deployment options In Lync Server 2013</A> 」を参照してください。<BR>以前のリリースでは、ユーザーに対して RCC とエンタープライズボイスの両方を有効にすることができましたが、デュアルフォーク用にユーザーを構成した場合に限り、着信呼び出しがユーザーの PBX 電話と Communicator を同時に呼び出す機能を有効にすることができます。 Lync Server 2010 では、デュアルフォークはサポートされていません。

    
    </div>

**msRTCSIP-line** 属性を設定するには、次の 3 つの方法があります。

  - Microsoft Identity Integration Server (推奨)

  - Lync Server コントロールパネルの [**ユーザー** ] ページ

多くの電話番号を処理する必要がある場合は、組織によって開発されたカスタムスクリプトを選択することをお勧めします。 組織が Active Directory ドメイン サービスで電話番号をどのように表しているかに応じて、スクリプトで主要電話番号を **msRTCSIP-line** 属性にコピーする前に E.164 形式に正規化することが必要になる場合があります。

  - 組織が Active Directory ドメイン サービスにすべての電話番号を同じ形式で保持しており、さらにその形式が E.164 である場合、スクリプトでは各主要電話番号を **msRTCSIP-line** 属性に書き込むだけで済みます。

  - Active Directory ドメイン サービスにすべての電話番号を同じ形式で保持している場合でも、その形式が E.164 ではないときには、スクリプトで適切な正規化ルールを定義して主要電話番号を既存の形式から E.164 に変換してから、**msRTCSIP-line** 属性に書き込む必要があります。

  - 組織が Active Directory ドメイン サービスで電話番号の標準形式を適用していない場合は、スクリプトで適切な正規化ルールを定義して主要電話番号をさまざまな形式から E.164 準拠に変換してから、**msRTCSIP-line** 属性に書き込む必要があります。

スクリプトでは、**msRTCSIP-line** 属性に主要電話番号を書き込む前に、各番号の前にプレフィックス **Tel:** を挿入することも必要となります。

この属性で指定する番号に求められる形式は次のとおりです。

  - Tel: + 14255550100; ext = 50100。

  - Tel:5550100 (企業全体で一意の内線番号の場合)
    
    <div>
    

    > [!IMPORTANT]  
    > アドレス帳サービス (ABS) によって実行される正規化では、Active Directory ドメイン サービス内で 各ユーザーの主要電話番号が置き換えられるわけではなく、正規化する必要性がなくなるわけでもありません。ABS は Active Directory ドメイン サービスにアクセスできないため、主要電話番号を <STRONG>msRTCSIP-line</STRONG> 属性にコピーできません。

    
    </div>

</div>

<div>

## <a name="step-2-enable-users-for-enterprise-voice"></a>ステップ 2. ユーザーをエンタープライズ VoIP に対して有効にする

有効化するユーザーを特定する以外に、このステップを完了するために必要な特別な計画はありません。

</div>

<div>

## <a name="step-3-prepare-dial-plans-for-users"></a>ステップ 3. ユーザー向けのダイヤル プランを準備する

エンタープライズ VoIP に対して有効にされたユーザーは、ダイヤル プランがないと PSTN へ電話をかけることができません。ダイヤル プランとは、電話番号の承認と通話のルーティングを目的として、特定の場所、個々のユーザー、または連絡先オブジェクトの電話番号を 1 つの標準形式 (E.164) に変換する正規化ルールのセットに名前を付けたものです。正規化ルールは、さまざまな形式で表現された電話番号を指定された各場所、ユーザー、または連絡先オブジェクトにルーティングする方法を定義します。

ダイヤルプランの準備の詳細については、「 [Lync Server 2013 のダイヤルプランと正規化ルール](lync-server-2013-dial-plans-and-normalization-rules.md)」を参照してください。

</div>

<div>

## <a name="step-4-plan-user-voice-policies"></a>ステップ 4. ユーザーの音声ポリシーを計画する

エンタープライズ VoIP に移動するユーザーについては、企業の電話から長距離通話や国際通話を利用する権利などの従来の PBX 上のユーザー クラス オブ サービス (CoS) 設定を VoIP ポリシーとして再構成する必要があります。 エンタープライズ Voip のポリシーの計画と作成の詳細については、「 [Lync Server 2013 の音声ポリシー](lync-server-2013-voice-policies.md)」を参照してください。

</div>

<div>

## <a name="step-5-plan-outbound-call-routes"></a>ステップ 5. 発信通話ルートを計画する

通話ルートは、Lync Server がエンタープライズ Voip ユーザーによって送信される発信呼び出しを処理する方法を指定します。 ユーザーが番号をダイヤルすると、サーバーは、必要に応じて、ダイヤル文字列を E.164 形式に正規化し、一致する SIP URI があるかどうかを調べます。 一致する SIP URI が見つからない場合は、番号に基づいて発信通話ルーティング ロジックが適用されます。 発信通話ルーティング ロジックを定義する最後のステップでは、ダイヤル プランごとの各相手電話番号に対して、個別の名前が付けられた通話ルートが作成されます。

通話ルートの計画の詳細については、「 [Lync Server 2013 の音声ルート](lync-server-2013-voice-routes.md)」を参照してください。

</div>

<div>

## <a name="step-6-configure-pbx-or-sip-trunk-to-reroute-calls-for-enterprise-voice-users"></a>ステップ 6. エンタープライズ VoIP に対して有効化されたユーザーの通話を再ルーティングするように PBX または SIP トランクを構成する

従来の PBX 接続または インターネット テレフォニー サービス プロバイダー (ITSP) への SIP トランク接続でこれまでホストされていたユーザーは、移動後も各自の電話番号を保持します。 唯一の要件は、移行後に、エンタープライズ Voip ユーザーの着信呼び出しを仲介サーバーにルーティングするように PBX または SIP トランクを再構成する必要があることです。

</div>

<div>

## <a name="step-7-move-users-to-exchange-unified-messaging-recommended"></a>ステップ 7. ユーザーを Exchange ユニファイド メッセージングに移動する (推奨)

Exchange ユニファイド メッセージングへのユーザーの移動は、次の作業で構成されます。

  - 連携して動作するように Exchange ユニファイドメッセージングと Lync Server を構成します。

  - Exchange ユニファイド メッセージングの通話応答と Outlook Voice Access に対してユーザーを有効にします。 Exchange ユニファイド メッセージング サーバーでこの作業を行います。 詳細については、「Exchange Server 2010 TechNet [http://go.microsoft.com/fwlink/p/?linkID=139372](http://go.microsoft.com/fwlink/p/?linkid=139372)ライブラリ」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

