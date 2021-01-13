---
title: Skype for Business Server のフロントエンド サーバー VoIP コンポーネント
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 変換サービスやエンタープライズ VoIPルーティング コンポーネントなど、Skype for Business Server のフロントエンド サーバー上に位置する新しいコンポーネントについて説明します。
ms.openlocfilehash: fcf1e30c0f6bbe0a292de54e4cc4b264774f9c7f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825657"
---
# <a name="front-end-server-voip-components-for-skype-for-business-server"></a>Skype for Business Server のフロントエンド サーバー VoIP コンポーネント

変換サービスやエンタープライズ VoIPルーティング コンポーネントなど、Skype for Business Server のフロントエンド サーバー上に位置する新しいコンポーネントについて説明します。

フロントエンド サーバー上にある VoIP コンポーネントは次のとおりです。

- 変換サービス

- 着信ルーティング コンポーネント

- 発信ルーティング コンポーネント

- Exchange UM ルーティング コンポーネント

- 内部クラスター ルーティング コンポーネント

- [Skype for Business Server の仲介サーバー コンポーネント](mediation-server.md)

## <a name="translation-service"></a>変換サービス

変換サービスは、ダイヤルされた電話番号を、管理者が定義した正規化ルールに基づいて E.164 形式またはその他の形式に変換するサーバー コンポーネントです。変換サービスでは、独自の番号付けシステムを使用する組織や E.164 をサポートしていないゲートウェイまたは PBX を使用する組織の場合は、E.164 以外の形式に変換できます。

## <a name="inbound-routing-component"></a>着信ルーティング コンポーネント

受信ルーティング コンポーネントは、ユーザーが自分のクライアントで指定した基本設定に基エンタープライズ VoIPします。 着信ルーティング コンポーネントはまた、ユーザーが設定した場合に、代理人着信および同時着信を行います。 たとえば、ユーザーは、不在時の着信を転送するか、それとも単に通知に記録するかを指定します。 着信の転送が有効になっている場合、ユーザーは、応答のない通話を別の番号に転送するか、通話応答を提供するように構成されている Exchange UM サーバーに転送するか指定できます。 受信ルーティング コンポーネントは、既定ですべての Standard Edition サーバーとフロントエンド サーバーにインストールされます。

## <a name="outbound-routing-component"></a>発信ルーティング コンポーネント

発信ルーティング コンポーネントは、発信通話を通話先の PBX または PSTN にルーティングします。 ユーザーの音声ポリシーで定義されている通話承認ルールを発信者に適用し、各通話のルーティングに最適な PSTN ゲートウェイを決定します。 発信ルーティング コンポーネントは、すべての Standard Edition サーバーとフロントエンド サーバーに既定でインストールされます。

発信ルーティング コンポーネントで使用されるルーティング ロジックは、主にネットワーク管理者またはテレフォニー管理者が組織の要件に従って構成します。

## <a name="exchange-um-routing-component"></a>Exchange UM ルーティング コンポーネント

Exchange UM ルーティング コンポーネントは、Skype for Business Server と Exchange ユニファイド メッセージング (UM) を実行しているサーバー間のルーティングを処理して、Skype for Business Server とユニファイド メッセージング機能を統合します。

Exchange UM ルーティング コンポーネントは、Exchange UM サーバーが使用できない場合にも、PSTN を使用したボイス メールの再ルーティングを処理します。 ブランチ サイトの エンタープライズ VoIP ユーザーが中央サイトへの回復力のある WAN リンクを持たない場合、ブランチ サイトで展開する存続可能ブランチ アプライアンスは、WAN の停止中にブランチ ユーザーにボイス メールの存続性を提供します。 WAN リンクを使用できない場合は、存続可能ブランチ アプライアンスは次を行います。

- セントラル サイトの Exchange ユニファイド メッセージング サーバーに、PSTN を介して不在時の着信を再ルーティングします。

- ユーザーが PSTN を介してボイス メール メッセージを取得できるようにします。

- 不在着信通知をキューに入れ、WAN リンクが回復した時に Exchange UM サーバーへそれらをアップロードします。

ボイス メールの再ルーティングを有効にするには、Exchange 管理者が Exchange UM 自動応答 (AA) を構成してメッセージのみを受け付けすることをお勧めします。

これらの機能の詳細については、「[On-Premises Exchange Unified Messaging Integration](https://technet.microsoft.com/library/e7c63a71-2d99-4aa9-b649-36c1a431bdf1.aspx)」および「[Planning for Enterprise Voice Resiliency](https://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx)」を参照してください。

## <a name="intercluster-routing-component"></a>内部クラスター ルーティング コンポーネント

Intercluster ルーティング コンポーネントは、呼び出しを呼び出し先のプライマリ レジストラー プールにルーティングします。 使用できない場合、コンポーネントは呼び出しを呼び出し先のバックアップ レジストラー プールにルーティングします。 呼び出し先のプライマリ レジストラー プールとバックアップ レジストラー プールが IP ネットワークを使用して到達できない場合、Intercluster ルーティング コンポーネントは PSTN を使用してユーザーの電話番号に通話を再ルーティングします。

## <a name="other-front-end-server-components-required-for-voip"></a>VoIP に必要なその他のフロントエンド サーバー コンポーネント

VoIP に不可欠なサポートを提供し、それ自体は VoIP コンポーネントではない、フロントエンド サーバーまたはディレクターに存在するその他のコンポーネントには、次のようなものがあります。

- **ユーザー サービス。** 各着信通話の通話先電話番号に対して逆引き番号検索を実行し、その電話番号を通話先ユーザーの SIP URI と照合します。 この情報を使用して、受信ルーティング コンポーネントは、そのユーザーの登録済み SIP エンドポイントに通話を分散します。 ユーザー サービスは、すべてのフロントエンド サーバーおよびディレクターのコア コンポーネントです。

- **ユーザー レプリケーター。** Active Directory ドメイン サービスからユーザーの電話番号を抽出し、ユーザー サービスとアドレス帳サーバーで使用できる RTC データベース内のテーブルに書き込みます。 ユーザー レプリケーターは、すべてのフロントエンド サーバーのコア コンポーネントです。

- **アドレス帳サーバー。** Active Directory ドメイン サービスから Skype for Business Server クライアントへのグローバル アドレス一覧情報を提供します。 また、RTC データベースからユーザーおよび連絡先情報を取得し、アドレス帳ファイルに情報を書き込み、Skype for Business クライアントがダウンロードする共有フォルダーにファイルを保存します。 アドレス帳サーバーは、この情報を RTCAb データベースに書き込みます。このデータベースは、アドレス帳 Web クエリ サービスが Skype for Business モバイルからのユーザー検索クエリに応答するために使用します。 必要に応じて、Skype for Business でユーザー連絡先をプロビジョニングするために RTC データベースに書き込まれるエンタープライズ ユーザーの電話番号を正規化します。 アドレス帳サービスは、既定ですべてのフロントエンド サーバーにインストールされます。 アドレス帳 Web クエリ サービスは、各フロントエンド サーバー上の Web サービスと一緒に既定でインストールされます。


