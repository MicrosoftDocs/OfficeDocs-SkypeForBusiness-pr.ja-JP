---
title: 'Lync Server 2013: フロントエンドサーバー VoIP コンポーネント'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Front End Server VoIP components
ms:assetid: 310e81a7-da45-47d4-95d0-92837e386502
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425812(v=OCS.15)
ms:contentKeyID: 48183765
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8bab5751fc0291047f3795731f379d1e14f5f12b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739737"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="front-end-server-voip-components-for-lync-server-2013"></a>Lync Server 2013 用のフロントエンドサーバー VoIP コンポーネント

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-01_

フロントエンドサーバーにある VoIP コンポーネントは、次のようになります。

  - 変換サービス

  - 着信ルーティング コンポーネント

  - 発信ルーティング コンポーネント

  - Exchange UM ルーティング コンポーネント

  - 内部クラスター ルーティング コンポーネント

  - [Lync Server 2013 の仲介サーバーコンポーネント](lync-server-2013-mediation-server-component.md)

<div>

## <a name="translation-service"></a>変換サービス

変換サービスは、ダイヤルされた電話番号を、管理者が定義した正規化ルールに基づいて E.164 形式またはその他の形式に変換するサーバー コンポーネントです。変換サービスでは、独自の番号付けシステムを使用する組織や E.164 をサポートしていないゲートウェイまたは PBX を使用する組織の場合は、E.164 以外の形式に変換できます。

</div>

<div>

## <a name="inbound-routing-component"></a>着信ルーティング コンポーネント

着信ルーティングコンポーネントは、エンタープライズボイスクライアント上のユーザーによって指定された環境設定に従って、着信通話を処理します。 また、着信ルーティング コンポーネントは、ユーザーが設定した場合に、代理人着信および同時着信を行います。 たとえば、ユーザーは、不在時の着信を転送するか、それとも単に通知として記録するかを指定します。 着信の転送が有効になっている場合、ユーザーは、不在着信を別の番号に転送するか、通話応答を提供するように構成されている Exchange UM サーバーに転送するかを指定できます。 着信ルーティングコンポーネントは、既定ですべての Standard Edition サーバーとフロントエンドサーバーにインストールされます。

</div>

<div>

## <a name="outbound-routing-component"></a>発信ルーティング コンポーネント

発信ルーティング コンポーネントは、発信通話を通話先の PBX または PSTN にルーティングします。 発信者に、ユーザーの音声ポリシーに定義された通話の承認ルールが適用され、それぞれの発信のルーティングに対して最適な PSTN ゲートウェイが決定されます。 送信ルーティングコンポーネントは、既定ですべての Standard Edition サーバーとフロントエンドサーバーにインストールされます。

発信ルーティング コンポーネントで使用されるルーティング ロジックは、主にネットワーク管理者またはテレフォニー管理者が組織の要件に従って構成します。

</div>

<div>

## <a name="exchange-um-routing-component"></a>Exchange UM ルーティング コンポーネント

Exchange UM ルーティングコンポーネントは、lync Server と Exchange ユニファイドメッセージング (UM) を実行しているサーバーの間のルーティングを処理します。これにより、Lync Server とユニファイドメッセージング機能が統合されます。

Exchange um ルーティングコンポーネントは、Exchange UM サーバーが利用できない場合に、PSTN 経由のボイスメールの再ルーティングも処理します。 セントラルサイトへの回復可能な WAN リンクを持っていない支社サイトのエンタープライズ Voip ユーザーがいる場合、ブランチサイトに展開した Survivable Branch Appliance は、WAN の停止中に支店ユーザー用のボイスメール survivability を提供します。 WAN リンクが利用できない場合、Survivable Branch Appliance は次の処理を実行します。

  - 中央サイトの Exchange ユニファイド メッセージング サーバーに、PSTN を介して不在時の着信を再ルーティングします。

  - ユーザーが PSTN を介してボイス メール メッセージを取得できるようにします。

  - 不在着信通知をキューに入れ、WAN リンクが回復したときに Exchange UM サーバーへそれらをアップロードします。

ボイスメールの再ルーティングを有効にするには、Exchange 管理者が Exchange UM 自動応答 (AA) でメッセージのみを受け入れるように構成することをお勧めします。

これらの機能の詳細については、「 [Lync server 2013 での Exchange ユニファイドメッセージングの統合計画](lync-server-2013-planning-for-exchange-unified-messaging-integration.md)」および「 [lync server 2013 でのエンタープライズボイスの回復性の計画](lync-server-2013-planning-for-enterprise-voice-resiliency.md)」を参照してください。

</div>

<div>

## <a name="intercluster-routing-component"></a>内部クラスター ルーティング コンポーネント

内部クラスター ルーティング コンポーネントは、通話を呼び出し先のプライマリ レジストラー プールにルーティングします。それが不可能な場合、コンポーネントは、通話を呼び出し先のバックアップ レジストラー プールにルーティングします。呼び出し先のプライマリ レジストラー プールおよびバックアップ レジストラー プールが IP ネットワークを介して到達不能の場合、内部クラスター ルーティング コンポーネントは PSTN を介して通話をユーザーの電話番号へ再ルーティングします。

</div>

<div>

## <a name="other-front-end-server-components-required-for-voip"></a>VoIP に必要なその他のフロント エンド サーバー コンポーネント

フロントエンドサーバーまたはディレクターに常駐するその他のコンポーネントは VoIP をサポートしていますが、VoIP コンポーネントには含まれていません。次のような機能を備えています。

  - **ユーザー サービス。** 各着信通話の通話先電話番号に対して逆引き番号検索を実行し、その電話番号を通話先ユーザーの SIP URI と照合します。 この情報を使用して、着信ルーティング コンポーネントはユーザーの登録 SIP エンドポイントに通話を分散します。 ユーザーサービスは、すべてのフロントエンドサーバーおよびディレクターのコアコンポーネントです。

  - **ユーザー レプリケーター。** Active Directory ドメインサービスからユーザーの電話番号を抽出し、RTC データベース内のテーブルに書き込みます。この機能は、ユーザーサービスとアドレス帳サーバーで利用できます。 ユーザーレプリケーターは、すべてのフロントエンドサーバー上のコアコンポーネントです。

  - **アドレス帳サーバー。** Active Directory ドメインサービスから Lync Server クライアントにグローバルアドレス一覧情報を提供します。 また、RTC データベースからユーザーと連絡先の情報を取得し、その情報をアドレス帳ファイルに書き込んだ後、Lync クライアントによってダウンロードされた共有フォルダーにファイルを保存します。 アドレス帳サーバーは、情報を RTCAb データベースに書き込みます。これは、アドレス帳 Web クエリサービスによって Microsoft Lync 2010 Mobile からのユーザー検索クエリに応答するために使用されます。 Lync でユーザーの連絡先をプロビジョニングする目的で、RTC データベースに書き込まれるエンタープライズユーザーの電話番号を、必要に応じて標準化します。 アドレス帳サービスは、既定ですべてのフロントエンドサーバーにインストールされます。 アドレス帳 Web クエリサービスは、各フロントエンドサーバー上の Web サービスに既定でインストールされます。

</div>

</div>

<span> </span>

</div>

</div>

</div>

