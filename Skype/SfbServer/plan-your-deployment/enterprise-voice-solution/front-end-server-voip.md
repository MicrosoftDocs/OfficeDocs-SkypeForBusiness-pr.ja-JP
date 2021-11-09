---
title: フロントエンド サーバー VoIP コンポーネント (Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 310e81a7-da45-47d4-95d0-92837e386502
description: 翻訳サービスやエンタープライズ VoIPルーティング コンポーネントなど、Skype for Business Server フロントエンド サーバー上にあるさまざまなコンポーネントについて説明します。
ms.openlocfilehash: d649185ccc83da925cc7341087d373d67523b5b6
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60850730"
---
# <a name="front-end-server-voip-components-for-skype-for-business-server"></a>フロントエンド サーバー VoIP コンポーネント (Skype for Business Server

翻訳サービスやエンタープライズ VoIPルーティング コンポーネントなど、Skype for Business Server フロントエンド サーバー上にあるさまざまなコンポーネントについて説明します。

フロント エンド サーバー上にある VoIP コンポーネントは次のとおりです。

- 変換サービス

- 着信ルーティング コンポーネント

- 発信ルーティング コンポーネント

- Exchange UM ルーティング コンポーネント

- 内部クラスター ルーティング コンポーネント

- [仲介サーバー コンポーネント (Skype for Business Server](mediation-server.md)

## <a name="translation-service"></a>変換サービス

変換サービスは、ダイヤルされた電話番号を、管理者が定義した正規化ルールに基づいて E.164 形式またはその他の形式に変換するサーバー コンポーネントです。変換サービスでは、独自の番号付けシステムを使用する組織や E.164 をサポートしていないゲートウェイまたは PBX を使用する組織の場合は、E.164 以外の形式に変換できます。

## <a name="inbound-routing-component"></a>着信ルーティング コンポーネント

受信ルーティング コンポーネントは、クライアント上のユーザーが指定した基本設定に従って、着信呼び出しをエンタープライズ VoIPします。 着信ルーティング コンポーネントはまた、ユーザーが設定した場合に、代理人着信および同時着信を行います。 たとえば、ユーザーは、不在時の着信を転送するか、それとも単に通知に記録するかを指定します。 通話転送が有効になっている場合、ユーザーは、応答されていない通話を別の番号に転送するか、通話応答を提供するように構成されている Exchange UM サーバーに転送するかどうかを指定できます。 受信ルーティング コンポーネントは、既定ですべてのサーバーとフロントエンド Standard Editionにインストールされます。

## <a name="outbound-routing-component"></a>発信ルーティング コンポーネント

発信ルーティング コンポーネントは、発信通話を通話先の PBX または PSTN にルーティングします。 ユーザーの音声ポリシーで定義されている通話承認ルールを発信者に適用し、各呼び出しをルーティングする最適な PSTN ゲートウェイを決定します。 送信ルーティング コンポーネントは、既定ではすべてのサーバーとフロントエンド Standard Editionにインストールされます。

発信ルーティング コンポーネントで使用されるルーティング ロジックは、主にネットワーク管理者またはテレフォニー管理者が組織の要件に従って構成します。

## <a name="exchange-um-routing-component"></a>Exchange UM ルーティング コンポーネント

この Exchange UM ルーティング コンポーネントは、Skype for Business Server と Exchange ユニファイド メッセージング (UM) を実行しているサーバー間のルーティングを処理し、Skype for Business Server をユニファイド メッセージング機能と統合します。

またExchange UM ルーティング コンポーネントは、UM サーバーが使用できない場合に PSTN を使用Exchangeルーティングも処理します。 ブランチ サイトに回復力のある WAN リンクを持つブランチ サイトに エンタープライズ VoIP ユーザーがいる場合、ブランチ サイトで展開する存続可能ブランチ アプライアンスは、WAN の停止中にブランチ ユーザーにボイス メールの存続性を提供します。 WAN リンクを使用できない場合は、存続可能ブランチ アプライアンスは次を行います。

- セントラル サイトの Exchange ユニファイド メッセージング サーバーに、PSTN を介して不在時の着信を再ルーティングします。

- ユーザーが PSTN を介してボイス メール メッセージを取得できるようにします。

- 不在着信通知をキューに入れ、WAN リンクが回復した時に Exchange UM サーバーへそれらをアップロードします。

ボイス メールの再ルーティングを有効にするには、メッセージのみを受け入Exchange UM Exchange (AA) 自動応答構成することをお勧めします。

これらの機能の詳細については、「[On-Premises Exchange Unified Messaging Integration](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-exchange-unified-messaging-integration)」および「[Planning for Enterprise Voice Resiliency](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-enterprise-voice-resiliency)」を参照してください。

## <a name="intercluster-routing-component"></a>内部クラスター ルーティング コンポーネント

Intercluster ルーティング コンポーネントは、呼び出し先のプライマリ レジストラー プールへの通話のルーティングを担当します。 使用できない場合、コンポーネントは呼び出し先のバックアップ レジストラー プールに呼び出しをルーティングします。 呼び出し先のプライマリ およびバックアップ レジストラー プールが IP ネットワーク上で到達できない場合、Intercluster ルーティング コンポーネントは PSTN を使用してユーザーの電話番号に通話を再ルーティングします。

## <a name="other-front-end-server-components-required-for-voip"></a>VoIP に必要なその他のフロントエンド サーバー コンポーネント

VoIP に不可欠なサポートを提供するフロントエンド サーバーまたはディレクターに存在する他のコンポーネントですが、それ自体は VoIP コンポーネントではありません。次のコンポーネントを使用します。

- **ユーザー サービス。** 各着信通話の通話先電話番号に対して逆引き番号検索を実行し、その電話番号を通話先ユーザーの SIP URI と照合します。 この情報を使用して、受信ルーティング コンポーネントは、そのユーザーの登録済み SIP エンドポイントに呼び出しを配布します。 User Services は、すべてのフロントエンド サーバーとディレクターのコア コンポーネントです。

- **ユーザー レプリケーター。** Active Directory ドメイン サービスからユーザーの電話番号を抽出し、RTC データベース内のテーブルに書き込み、ユーザー サービスとアドレス帳サーバーで使用できます。 ユーザー レプリケーターは、すべてのフロントエンド サーバーのコア コンポーネントです。

- **アドレス帳サーバー。** Active Directory ドメイン サービスからクライアントへのグローバル アドレス一覧Skype for Business Serverします。 また、RTC データベースからユーザーと連絡先情報を取得し、アドレス帳ファイルに情報を書き込み、Skype for Business クライアントがダウンロードする共有フォルダーにファイルを保存します。 アドレス帳サーバーは RTCAb データベースに情報を書き込みます。このデータベースは、モバイルからのユーザー検索クエリに応答するためにアドレス帳 Web クエリ サービスSkype for Businessします。 必要に応じて、RTC データベースに書き込まれるエンタープライズ ユーザーの電話番号を正規化し、ユーザー連絡先のプロビジョニングを目的Skype for Business。 アドレス帳サービスは、既定ですべてのフロントエンド サーバーにインストールされます。 アドレス帳 Web クエリ サービスは、既定で各フロントエンド サーバー上の Web サービスと一緒にインストールされます。