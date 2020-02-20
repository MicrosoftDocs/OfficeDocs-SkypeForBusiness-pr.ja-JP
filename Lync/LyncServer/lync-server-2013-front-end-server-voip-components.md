---
title: 'Lync Server 2013: フロントエンドサーバーの VoIP コンポーネント'
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
ms.openlocfilehash: 0be06c357fd3b02b2a44f4ba8f4aebfaab99f609
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147480"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="front-end-server-voip-components-for-lync-server-2013"></a>Lync Server 2013 のフロントエンドサーバーの VoIP コンポーネント

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-01_

フロントエンドサーバーにある VoIP コンポーネントは次のとおりです。

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

着信ルーティングコンポーネントは、エンタープライズ Voip クライアントでユーザーによって指定された設定に基づいて、着信呼び出しを処理します。 着信ルーティング コンポーネントはまた、ユーザーが設定した場合に、代理人着信および同時着信を行います。 たとえば、ユーザーは、不在時の着信を転送するか、それとも単に通知に記録するかを指定します。 着信の転送が有効になっている場合、ユーザーは、応答のない通話を別の番号に転送するか、通話応答を提供するように構成された Exchange UM サーバーに転送するかを指定できます。 着信ルーティングコンポーネントは、すべての Standard Edition サーバーとフロントエンドサーバーに既定でインストールされます。

</div>

<div>

## <a name="outbound-routing-component"></a>発信ルーティング コンポーネント

発信ルーティング コンポーネントは、発信通話を通話先の PBX または PSTN にルーティングします。 発信者に、ユーザーの音声ポリシーに定義された通話の承認ルールが適用され、それぞれの発信のルーティングに対して最適な PSTN ゲートウェイが決定されます。 送信ルーティングコンポーネントは、すべての Standard Edition サーバーとフロントエンドサーバーに既定でインストールされます。

発信ルーティング コンポーネントで使用されるルーティング ロジックは、主にネットワーク管理者またはテレフォニー管理者が組織の要件に従って構成します。

</div>

<div>

## <a name="exchange-um-routing-component"></a>Exchange UM ルーティング コンポーネント

Exchange UM ルーティングコンポーネントは、lync Server と Exchange ユニファイドメッセージング (UM) を実行しているサーバーとの間のルーティングを処理して、Lync Server とユニファイドメッセージング機能を統合します。

Exchange um ルーティングコンポーネントは、Exchange UM サーバーが利用できない場合に、PSTN を介したボイスメールの再ルーティングも処理します。 中央サイトへの復元可能な WAN リンクを持たない支社サイトにエンタープライズ Voip ユーザーがいる場合、ブランチサイトに展開する存続可能ブランチアプライアンスは、WAN の停止時にブランチユーザーにボイスメール存続性を提供します。 WAN リンクを使用できない場合は、存続可能ブランチ アプライアンスは次を行います。

  - セントラル サイトの Exchange ユニファイド メッセージング サーバーに、PSTN を介して不在時の着信を再ルーティングします。

  - ユーザーが PSTN を介してボイス メール メッセージを取得できるようにします。

  - 不在着信通知をキューに入れ、WAN リンクが回復した時に Exchange UM サーバーへそれらをアップロードします。

ボイスメールの再ルーティングを有効にするには、Exchange 管理者が Exchange UM 自動応答 (AA) を構成してメッセージのみを受け入れるようにすることをお勧めします。

これらの機能の詳細については、「lync server [2013 での Exchange ユニファイドメッセージング統合の計画](lync-server-2013-planning-for-exchange-unified-messaging-integration.md)」および「 [lync server 2013 でのエンタープライズ voip の復元の計画](lync-server-2013-planning-for-enterprise-voice-resiliency.md)」を参照してください。

</div>

<div>

## <a name="intercluster-routing-component"></a>内部クラスター ルーティング コンポーネント

内部クラスター ルーティング コンポーネントは、通話を呼び出し先のプライマリ レジストラー プールにルーティングします。 それが不可能な場合、コンポーネントは、通話を呼び出し先のバックアップ レジストラー プールにルーティングします。 呼び出し先のプライマリ レジストラー プールおよびバックアップ レジストラー プールが IP ネットワークを介して到達不能の場合、内部クラスター ルーティング コンポーネントは PSTN を介して通話をユーザーの電話番号へ再ルーティングします。

</div>

<div>

## <a name="other-front-end-server-components-required-for-voip"></a>VoIP に必要なその他のフロントエンド サーバー コンポーネント

フロントエンドサーバーまたはディレクターに搭載されているその他のコンポーネントは、VoIP のサポートを提供しますが、それ自体は VoIP コンポーネントではありません。次のようなものがあります。

  - **ユーザー サービス。** 各着信通話の通話先電話番号に対して逆引き番号検索を実行し、その電話番号を通話先ユーザーの SIP URI と照合します。 この情報を使用して、着信ルーティング コンポーネントはユーザーの登録 SIP エンドポイントに通話を分散します。 ユーザーサービスは、すべてのフロントエンドサーバーおよびディレクターのコアコンポーネントです。

  - **ユーザー レプリケーター。** Active Directory ドメインサービスからユーザーの電話番号を抽出し、それらを RTC データベースのテーブルに書き込みます。これは、ユーザーサービスとアドレス帳サーバーで利用できます。 ユーザーレプリケーターは、すべてのフロントエンドサーバー上のコアコンポーネントです。

  - **アドレス帳サーバー。** Active Directory ドメインサービスから Lync Server クライアントへのグローバルアドレス一覧情報を提供します。 また、RTC データベースからのユーザー情報と連絡先情報を取得し、その情報をアドレス帳ファイルに書き込んだ後、それらのファイルを、Lync クライアントによってダウンロードされる共有フォルダーに格納します。 アドレス帳サーバーは、情報を RTCAb データベースに書き込みます。このデータベースは、アドレス帳 Web クエリサービスによって、Microsoft Lync 2010 Mobile からのユーザー検索クエリに応答するために使用されます。 必要に応じて、Lync でユーザーの連絡先をプロビジョニングする目的で RTC データベースに書き込まれるエンタープライズユーザーの電話番号を正規化します。 既定では、すべてのフロントエンドサーバーにアドレス帳サービスがインストールされます。 既定では、アドレス帳 Web クエリサービスは各フロントエンドサーバー上の Web サービスと共にインストールされます。

</div>

</div>

<span> </span>

</div>

</div>

</div>

