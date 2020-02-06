---
title: Skype for Business Server 用のフロントエンドサーバー VoIP コンポーネント
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 310e81a7-da45-47d4-95d0-92837e386502
description: 翻訳サービスやさまざまなルーティングコンポーネントなど、Skype for Business Server のフロントエンドサーバーにあるエンタープライズボイスコンポーネントについて説明します。
ms.openlocfilehash: eae2f389720a6c359f442a7a163d5b4b5aef6e26
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802967"
---
# <a name="front-end-server-voip-components-for-skype-for-business-server"></a>Skype for Business Server 用のフロントエンドサーバー VoIP コンポーネント

翻訳サービスやさまざまなルーティングコンポーネントなど、Skype for Business Server のフロントエンドサーバーにあるエンタープライズボイスコンポーネントについて説明します。

フロントエンドサーバーにある VoIP コンポーネントは、次のようになります。

- 変換サービス

- 着信ルーティング コンポーネント

- 発信ルーティング コンポーネント

- Exchange UM ルーティング コンポーネント

- 内部クラスター ルーティング コンポーネント

- [Skype for Business Server の仲介サーバーコンポーネント](mediation-server.md)

## <a name="translation-service"></a>変換サービス

変換サービスは、ダイヤルされた電話番号を、管理者が定義した正規化ルールに基づいて E.164 形式またはその他の形式に変換するサーバー コンポーネントです。変換サービスでは、独自の番号付けシステムを使用する組織や E.164 をサポートしていないゲートウェイまたは PBX を使用する組織の場合は、E.164 以外の形式に変換できます。

## <a name="inbound-routing-component"></a>着信ルーティング コンポーネント

着信ルーティングコンポーネントは、エンタープライズボイスクライアント上のユーザーによって指定された環境設定に従って、着信通話を処理します。 また、着信ルーティング コンポーネントは、ユーザーが設定した場合に、代理人着信および同時着信を行います。 たとえば、ユーザーは、不在時の着信を転送するか、それとも単に通知として記録するかを指定します。 着信の転送が有効になっている場合、ユーザーは、不在着信を別の番号に転送するか、通話応答を提供するように構成されている Exchange UM サーバーに転送するかを指定できます。 着信ルーティングコンポーネントは、既定ですべての Standard Edition サーバーとフロントエンドサーバーにインストールされます。

## <a name="outbound-routing-component"></a>発信ルーティング コンポーネント

発信ルーティング コンポーネントは、発信通話を通話先の PBX または PSTN にルーティングします。 ユーザーのボイスポリシーによって定義された通話承認規則が発信者に適用され、各通話をルーティングするための最適な PSTN ゲートウェイが決定されます。 送信ルーティングコンポーネントは、既定ですべての Standard Edition サーバーとフロントエンドサーバーにインストールされます。

発信ルーティング コンポーネントで使用されるルーティング ロジックは、主にネットワーク管理者またはテレフォニー管理者が組織の要件に従って構成します。

## <a name="exchange-um-routing-component"></a>Exchange UM ルーティング コンポーネント

Exchange UM ルーティングコンポーネントは、skype for Business Server と Exchange ユニファイドメッセージング (UM) を実行しているサーバーの間のルーティングを処理します。これにより、Skype for business Server とユニファイドメッセージング機能が統合されます。

Exchange um ルーティングコンポーネントは、Exchange UM サーバーが利用できない場合に、PSTN 経由のボイスメールの再ルーティングも処理します。 セントラルサイトへの回復可能な WAN リンクを持っていない支社サイトのエンタープライズ Voip ユーザーがいる場合、ブランチサイトに展開した Survivable Branch Appliance は、WAN の停止中に支店ユーザー用のボイスメール survivability を提供します。 WAN リンクが利用できない場合、Survivable Branch Appliance は次の処理を実行します。

- 中央サイトの Exchange ユニファイド メッセージング サーバーに、PSTN を介して不在時の着信を再ルーティングします。

- ユーザーが PSTN を介してボイス メール メッセージを取得できるようにします。

- 不在着信通知をキューに入れ、WAN リンクが回復したときに Exchange UM サーバーへそれらをアップロードします。

ボイスメールの再ルーティングを有効にするには、Exchange 管理者が Exchange UM 自動応答 (AA) でメッセージのみを受け入れるように構成することをお勧めします。

これらの機能の詳細については、「[On-Premises Exchange Unified Messaging Integration](https://technet.microsoft.com/library/e7c63a71-2d99-4aa9-b649-36c1a431bdf1.aspx)」および「[Planning for Enterprise Voice Resiliency](https://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx)」を参照してください。

## <a name="intercluster-routing-component"></a>内部クラスター ルーティング コンポーネント

Intercluster ルーティングコンポーネントは、呼び出し先のプライマリレジストラープールへの呼び出しをルーティングする役割を担います。 それが利用できない場合、コンポーネントは呼び出し元のバックアップレジストラープールに呼び出しをルーティングします。 呼び出し先のプライマリとバックアップのレジストラープールが IP ネットワーク経由で接続されていない場合、Intercluster ルーティングコンポーネントによって、着信が PSTN 経由でユーザーの電話番号に再ルーティングされます。

## <a name="other-front-end-server-components-required-for-voip"></a>VoIP に必要なその他のフロント エンド サーバー コンポーネント

フロントエンドサーバーまたはディレクターに常駐するその他のコンポーネントは VoIP をサポートしていますが、VoIP コンポーネントには含まれていません。次のような機能を備えています。

- **ユーザー サービス。** 各着信通話の通話先電話番号に対して逆引き番号検索を実行し、その電話番号を通話先ユーザーの SIP URI と照合します。 この情報を使って、着信ルーティングコンポーネントによって、ユーザーの登録済み SIP エンドポイントへの通話が配布されます。 ユーザーサービスは、すべてのフロントエンドサーバーおよびディレクターのコアコンポーネントです。

- **ユーザー レプリケーター。** Active Directory ドメインサービスからユーザーの電話番号を抽出し、RTC データベース内のテーブルに書き込みます。この機能は、ユーザーサービスとアドレス帳サーバーで利用できます。 ユーザーレプリケーターは、すべてのフロントエンドサーバー上のコアコンポーネントです。

- **アドレス帳サーバー。** Active Directory ドメインサービスから Skype for Business Server クライアントにグローバルアドレス一覧情報を提供します。 また、RTC データベースからユーザーと連絡先の情報を取得し、その情報をアドレス帳ファイルに書き込んだ後、Skype for Business クライアントによってダウンロードされた共有フォルダーにファイルを保存します。 アドレス帳サーバーは、情報を RTCAb データベースに書き込みます。これは、アドレス帳 Web クエリサービスが Skype for Business mobile からユーザー検索クエリに応答するために使用されます。 必要に応じて、Skype for Business でユーザーの連絡先をプロビジョニングするために、RTC データベースに記載されているエンタープライズユーザーの電話番号を正規化します。 アドレス帳サービスは、既定ですべてのフロントエンドサーバーにインストールされます。 アドレス帳 Web クエリサービスは、各フロントエンドサーバー上の Web サービスに既定でインストールされます。


