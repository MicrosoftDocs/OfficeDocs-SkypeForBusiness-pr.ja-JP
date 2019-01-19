---
title: クラウド ボイスメール サービスを計画します。PBX の Skype ビジネス サーバー 2019
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: この資料では、利点、計画に関する考慮事項、およびマイクロソフトのクラウドのボイスメール サービスを実装するための要件について説明します。 クラウドのボイス メールの構成方法の詳細については、クラウドのボイスメールを設定するを参照してください。
ms.openlocfilehash: d1e962f36cdefafdd1efa2d02a719eed1d2e93fd
ms.sourcegitcommit: 716d39077784417c3545a91e501ae26ff56ebdf4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/19/2019
ms.locfileid: "29349024"
---
# <a name="plan-cloud-voicemail-service"></a>クラウドのボイスメール サービスを計画します。

## <a name="overview"></a>概要

この資料では、利点、計画に関する考慮事項、およびマイクロソフトのクラウドのボイスメール サービスを実装するための要件について説明します。 クラウドのボイス メールの構成方法の詳細については、[クラウドのボイス メールを構成するサービス](configure-cloud-voicemail.md)を参照してください。

クラウドのボイスメールに代わる Exchange ユニファイド メッセージング (UM) のメッセージング機能をユーザーのためビジネス 2019年音声 2019 の Exchange Server または Exchange Online にメールボックスを持つ Skype の音声を提供することにします。 ボイスメールのクラウドでは、オンプレミスとオンラインのユーザーの両方の次の利点があります。

- ボイスメールへの応答と預金の機能と強化された音声認識議事録

- ビジネス オンラインまたは Outlook クライアントで、Skype を使用して、ユーザーの Exchange メールボックスにボイス メールへのアクセス

- ボイスメールのオプションを管理するために Office 365 の web ベースのポータルを使用する機能

- Exchange のメールボックスをオンプレミスとクラウドのためのサポート

- オンライン ユニファイド メッセージングから既存のユーザーの応答メッセージの活用

機能比較の詳細については、 [Skype ビジネス サーバーと Exchange Server の移行のための計画](plan-um-migration.md)を参照してください。

メールボックスが Exchange Server の以前のバージョンでは、ユーザーの Exchange UM を使用するビジネス サーバー 2019 の Skype を継続 (2013、2016)。  ビジネス サーバーの Exchange Server と Skype に基づいているのボイスメール ソリューションを使用するを理解するバージョンは、ビジネス サーバー 2019 2019 の Exchange Server のいずれかの Skype への移行の計画の重要な部分です。 移行と相互運用性に関する詳細については、 [Skype ビジネス サーバーと Exchange Server の移行のための計画](plan-um-migration.md)を参照してください。

クラウドのボイスメールを使用ため、管理作業を大幅に合理化します。

- Exchange UM の役割を構成する必要はありません。
- クラウドのボイスメールの設定作業は簡単です。
- ボイスメール機能への更新は、ユーザーでは、累積的な更新 (CUs) に以下の依存関係の更新プログラム、最新の機能へのアクセスを常があるので、クラウドに直接配信されます。
- 設置とオンラインの Exchange メールボックスの両方のコントロールの同じセットがあります。 これらのコントロールの詳細については、[電話システムのボイス メールの設定](https://support.office.com/en-us/article/Set-up-Phone-System-voicemail-Admin-help-9c590873-b014-4df3-9e27-1bb97322a79d?ui=en-US&rs=en-US&ad=US)を参照してください。

次の図は、ハイブリッド展開でのクラウドのボイスメールを示しています。

![デバイス クラウドのボイスメール](../../sfbserver2019/media/plan-cloud-voice-mail-server1.png)

不在時の着信は、次のように処理されます。  

1. 社内のビジネス 2019年の Skype に所属していたユーザーの不在時の着信に送信されます設置 Skype でビジネス サーバーのオンラインのボイスメールのクラウド サービス。
2. サービスでは、議事録を含め、ボイス メールを処理します。
3. サービスにより、ボイスメール、ユーザーの Exchange メールボックスでメールボックスがオンプレミスであるかどうかまたはオンラインです。  
4. ユーザーからアクセスできる、ボイス メールいずれかのビジネスまたは Outlook クライアント用の Skype です。

## <a name="requirements"></a>要件

次の要件では、ビジネス サーバーのトポロジでサポートされている展開の Skype が既にあることを前提としています。  お客様の要件は、シナリオによって異なります。

- 既にを使用している Exchange UM オンライン ビジネス 2019年の Skype にアップグレードする場合は、ホスト ボイスメール ポリシーを変更し、ホスティング プロバイダーが正しく設定されていることを確認する必要があります。 詳細については、[クラウドのボイス メールを構成するサービス](configure-cloud-voicemail.md)を参照してください。

- 使用している Exchange UM の社内、または、オンライン、社内設置型の Exchange UM を使用するユーザーが混在している場合、必要がありますを変更して、ホスト ボイス メール ポリシーとホストのプロバイダー。  詳細については、[クラウドのボイス メールを構成するサービス](configure-cloud-voicemail.md)を参照してください。

- クラウドのボイスメールの新しい構成では、[クラウドのボイス メールを構成するサービス](configure-cloud-voicemail.md)に記載されている手順に従います。

上記の要件に加えて、要件を満たしてマイクロソフト クラウド ボイスメール サービスへの接続を構成する必要があります。

- ハイブリッド接続です。 ビジネス サーバーが展開されると、Skype が既にある、オンプレミス ユーザーのクラウドのボイスメールを有効にする場合は、ハイブリッド接続の設置とオンライン環境の設定があることを確認する必要があります。 分割ドメインの構成とも呼びます。

   詳細については、 [Skype ビジネス サーバーと Office 365 の間のハイブリッドの接続を計画](plan-hybrid-connectivity.md)し、 [Skype ビジネス サーバーと Office 365 の間のハイブリッド接続の構成](configure-hybrid-connectivity.md)を参照してください。

- オンプレミス ユーザーはエンタープライズ VoIP と Skype でボイスメールをホストのビジネス サーバーに対して有効にする必要があります。

- 外部の Exchange Web サービス (EWS) を URL と自動検出を設定する必要がありますまたはいくつかのクラウドのボイスメール機能が制限されます。

- 設置のみ deployment& #x 2014; がある場合は、のみを交換し Skype ビジネスの設置 servers& #x やり取りできます。 ですが、ボイスメールのクラウドを利用する、ライセンスを追加する必要はありません。

## <a name="migration-and-interoperability"></a>移行と相互運用性

Skype をビジネス サーバー 2019/2019 の Exchange Server の展開を計画している場合は、ボイス メッセージングの継続的なサービスを保証するには、慎重に、移行を計画する必要があります。 以下の点について留意してください。

- Exchange Server 2019 Exchange UM の機能が提供されなくなります
- Skype ビジネス サーバー 2019 の不要になったとの統合オンライン UM

バージョンの相互運用性とクラウドのボイスメールのトポロジがサポートされているが、Skype を比較する次の表に記載されているビジネス サーバーのバージョンのユーザー可能性がありますホームは、Exchange メールボックスを提供する可能性のあるバージョンとします。 クラウドのボイスメールは、ビジネス サーバーと Exchange Server 2019、Exchange オンラインの Skype でのみ機能します。

| | Exchange Server 2013 | Exchange Server 2016 | Exchange Server 2019 | Exchange Online   |
|:---    |:--- |:--- |:--- |:---  |
| Skype ビジネス サーバー 2019 | UM を Exchange Server | UM を Exchange Server | クラウドのボイスメール | クラウドのボイスメール
Skype for Business Server 2015 | UM を Exchange Server | UM を Exchange Server |  | クラウドのボイスメール <br> Exchange オンライン UM * |
Lync Server 2013 <br>  | UM を Exchange Server | UM を Exchange Server | | クラウドのボイスメール <br> Exchange オンライン UM * |

\*まで、使用されなくなりました。

マイクロソフトは、次の移行方法をお勧めします。

- ビジネス サーバー 2019 の Skype にアップグレードする場合は、Exchange Server 2013 または 2016、Exchange UM を使用することができますが、2019 の Exchange Server を使用している場合、クラウドのボイスメールにアップグレードする必要があります。
- 2019 の Exchange Server をアップグレードすると、Skype のビジネス サーバー ボイス メッセージングの UM の Exchange Server の以前のバージョンを使用して、アップグレードする Skype をビジネス サーバー 2019 メールボックス アップグレードする前にお勧めします。  それ以外の場合、ボイス メッセージ機能は失われます。

移行を計画の詳細については、 [Skype ビジネス サーバーと Exchange Server の移行のための計画](plan-um-migration.md)を参照してください。
