---
title: 'Lync Server 2013: エンタープライズ VoIP へのユーザーの移行'
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
ms.openlocfilehash: e92f0a7d71d42d8551a51028afec209e795941d5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756691"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="moving-users-to-enterprise-voice-in-lync-server-2013"></a>Lync Server 2013 でのエンタープライズ VoIP へのユーザーの移行

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-18_

既存の PBX テレフォニーインフラストラクチャからエンタープライズ Voip にユーザーを移動する場合、展開プロセスには、「 [Lync Server 2013 でのエンタープライズ voip の計画](lync-server-2013-planning-for-enterprise-voice.md)」で説明されている計画プロセスに含まれていないいくつかの手順が含まれます。 以前のエンタープライズ Voip 展開からユーザーを移行する方法については、インストールメディアに含まれている移行ドキュメントを参照してください。

既存のテレフォニーインフラストラクチャからエンタープライズボイスにユーザーを移動するプロセスは、次の手順で構成されます。

1.  主要な電話番号を指定します。

2.  エンタープライズ VoIP に対してユーザーを有効化します。

3.  ユーザー向けにダイヤルプランを準備します。

4.  ユーザーの音声ポリシーを計画します。

5.  通話ルートを計画します。

6.  PBX または SIP トランクを構成して、エンタープライズ Voip を有効にしているユーザーの通話を再ルーティングします。

7.  Exchange ユニファイドメッセージング (UM) にユーザーを移動する (推奨)

このトピックでは、これらの各手順に必要な計画について説明します。

<div>

## <a name="step-1-designate-primary-phone-numbers"></a>手順1 主要な電話番号を指定する

エンタープライズボイスは、音声を他のメッセージメディアと統合します。着信がサーバーに到着すると、サーバーはその番号をユーザーの SIP URI にマップし、その SIP URI に関連付けられているすべてのクライアントエンドポイントへの呼び出しをフォークします。 このプロセスでは、各ユーザーが通常の電話番号に関連付けられている必要があります。

主要な電話番号は、次のようにする必要があります。

  - グローバル一意または内部拡張の場合は、企業内で一意。

  - 企業内での所有者とルーティング経路。 個人番号は使用しないでください。

エンタープライズユーザーは、Active Directory ドメインサービスで2つ以上の電話番号を表示することができます。 特定のユーザーに関連付けられているすべての電話番号は、[Active Directory ユーザーとコンピューター] スナップインで、そのユーザーのプロパティシートで確認または変更することができます。

[**ユーザーのプロパティ**] ダイアログボックスの [**全般**] タブの [**電話番号**] ボックスには、ユーザーの主要作業番号が含まれている必要があります。 通常、この番号はユーザーのプライマリ電話番号として指定されます。

一部のユーザーは、特別な要件がある場合があります (たとえば、すべての着信通話を管理アシスタント経由でルーティングする場合など)。ただし、そのような例外は、必要な情報が明らかで重要である場合にのみ制限する必要があります。

1つ目の番号を選ぶと、次のようになります。

  - 可能な限り、E-164 形式に正規化されます。

  - Active Directory **msrtcsip-userenabled true line**属性にコピーされます。
    
    <div>
    

    > [!NOTE]  
    > <STRONG>リモート通話コントロール (RCC) との共存</STRONG><BR>RCC は、Lync Server を使用して、デスクトップ PBX 携帯電話を監視および制御する機能です。 コントロールはサーバー経由でルーティングされ、PBX へのゲートウェイとして機能します。 RCC とエンタープライズボイスの両方のユーザーを構成することはできませんが、[Line URI] の設定ではどちらの場合でも、ユーザーのプライマリ電話番号を指定します。<BR>選択したユーザーが引き続き使用できるようにする既存の PBX インフラストラクチャがある場合は、エンタープライズボイスを組織に段階的に導入することができます。 この展開シナリオの詳細については、計画ドキュメントの「 <A href="lync-server-2013-direct-sip-deployment-options.md">SIP 展開オプションと Lync Server 2013」</A>を参照してください。<BR>以前のリリースでは、ユーザーに対して RCC とエンタープライズボイスの両方を有効にすることができます。ただし、デュアルフォーク用にユーザーを構成している場合のみ、着信時にユーザーの PBX 電話と Communicator が同時に呼び出されます。 Lync Server 2010 では、デュアルフォーキングはサポートされていません。

    
    </div>

**Msrtcsip-userenabled true**属性を設定するには、次の3つの方法があります。

  - Microsoft Identity Integration Server (推奨)

  - Lync Server コントロールパネルの [**ユーザー** ] ページ

いくつかの電話番号を処理する必要があるので、組織によって開発されたスクリプトが適しています。 Active Directory ドメインサービスでの電話番号の表示方法によっては、スクリプトは、プライマリ電話番号を Msrtcsip-userenabled true 形式に正規化してから、それらを**line**属性にコピーする必要があります。

  - 組織で Active Directory ドメインサービスのすべての電話番号を1つの形式で管理していて、その形式が E.i の場合、スクリプトでは、各主要な電話番号を Msrtcsip-userenabled true 属性に書き込むだけで**対応**する必要があります。

  - 組織で Active Directory ドメインサービスのすべての電話番号を1つの形式で管理しているが、その形式が E.i ではない場合、スクリプトでは、プライマリ電話番号を既存の形式から**msrtcsip-userenabled true**に変換する前に、対応する正規化ルールを定義する必要があります。

  - 組織で Active Directory ドメインサービスの電話番号の標準形式を適用していない場合は、主要な電話番号を**msrtcsip-userenabled true line**属性に書き込む前に、主要な電話番号をさまざまな形式から e.i コンプライアンスに変換するために、スクリプトで適切な正規化ルールを定義する必要があります。

また、スクリプトでは、 **msrtcsip-userenabled true**属性に書き込む前に、各プライマリ番号の前に " **Tel** " というプレフィックスを挿入する必要があります。

この属性で指定する数値の予期される形式は、次のとおりです。

  - Tel: + 14255550100; ext = 50100

  - Tel: 5550100 (エンタープライズ規模の固有の拡張機能)
    
    <div>
    

    > [!IMPORTANT]  
    > アドレス帳サービス (ABS) によって実行される正規化によって、active Directory ドメインサービスへのアクセス権がなく、また、プライマリ番号を<STRONG>msrtcsip-userenabled true</STRONG>属性にコピーできないことが原因で、Active Directory ドメインサービスで各ユーザーの主要な電話番号を正規化する必要がなくなります。

    
    </div>

</div>

<div>

## <a name="step-2-enable-users-for-enterprise-voice"></a>手順2 エンタープライズ VoIP に対するユーザーの有効化

有効にするユーザーを特定する以外に、この手順を完了するために特別な計画は必要ありません。

</div>

<div>

## <a name="step-3-prepare-dial-plans-for-users"></a>手順3 ユーザー向けにダイヤルプランを準備します。

エンタープライズ Voip を有効にしているユーザーは、ダイヤルプランを使わずに PSTN に通話することはできません。 ダイヤル プランとは、電話番号の承認と通話のルーティングを目的として、特定の場所、個々のユーザー、または連絡先オブジェクトの電話番号を 1 つの標準形式 (E.164) に変換する正規化ルールのセットに名前を付けたものです。 正規化ルールは、さまざまな形式で表現された電話番号を指定された各場所、ユーザー、または連絡先オブジェクトにルーティングする方法を定義します。

ダイヤルプランを準備する方法については、「 [Lync Server 2013 のダイヤルプランと正規化ルール](lync-server-2013-dial-plans-and-normalization-rules.md)」を参照してください。

</div>

<div>

## <a name="step-4-plan-user-voice-policies"></a>手順4。 ユーザーの音声ポリシーを計画する

会社の電話から長距離または国際通話を発信する権利など、従来の PBX でのユーザークラスの設定は、エンタープライズ voip に移行されたユーザーのために VoIP ポリシーとして再構成する必要があります。 エンタープライズ Voip のポリシーの計画と作成について詳しくは、「 [Lync Server 2013 の音声ポリシー](lync-server-2013-voice-policies.md)」をご覧ください。

</div>

<div>

## <a name="step-5-plan-outbound-call-routes"></a>手順5 発信通話ルーティングを計画する

通話ルートは、Lync Server がエンタープライズボイスユーザーによる発信通話をどのように処理するかを指定します。 ユーザーが番号をダイヤルすると、サーバーは、必要に応じて、ダイヤル文字列を E.i 形式に標準化し、SIP URI と一致させようとします。 サーバーで一致させることができない場合は、その番号に基づいて発信呼び出しのルーティングロジックが適用されます。 ロジックを定義するための最後の手順では、各ダイヤルプランに記載されている宛先電話番号のセットごとに、個別の名前付き通話ルートを作成します。

通話ルートの計画について詳しくは、「 [Lync Server 2013 のボイスルーティング](lync-server-2013-voice-routes.md)」をご覧ください。

</div>

<div>

## <a name="step-6-configure-pbx-or-sip-trunk-to-reroute-calls-for-enterprise-voice-users"></a>手順6 エンタープライズボイスユーザーの通話の経路を変更するために PBX または SIP トランクを構成する

以前は、従来の PBX または SIP トランクでインターネットテレフォニーサービスプロバイダ (ITSP) にホストされていたユーザーは、移動後も電話番号を維持します。 唯一の要件として、移動後、PBX または SIP トランクを再構成して、エンタープライズ Voip ユーザーの着信通話を仲介サーバーにルーティングする必要があります。

</div>

<div>

## <a name="step-7-move-users-to-exchange-unified-messaging-recommended"></a>手順7 ユーザーを Exchange ユニファイドメッセージングに移行する (推奨)

Exchange ユニファイドメッセージングにユーザーを移行するには、次のタスクが含まれます。

  - 共同作業のために Exchange ユニファイドメッセージングと Lync Server を構成します。

  - ユーザーが Exchange ユニファイドメッセージングの通話応答と Outlook Voice Access を使用できるようにします。 このタスクは、Exchange ユニファイドメッセージングサーバー上で実行されます。 詳細については、「Exchange Server 2010 TechNet [http://go.microsoft.com/fwlink/p/?linkID=139372](http://go.microsoft.com/fwlink/p/?linkid=139372)ライブラリ」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

