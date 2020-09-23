---
title: Microsoft Teams のポリシー制御の概要
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: majaisin
description: Microsoft Teams のポリシー制御の概要。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3665f386f43d8e9b8c49a024663265c25ae96214
ms.sourcegitcommit: 448606977ee67befbdc91060363cf90dd346a528
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2020
ms.locfileid: "48136045"
---
# <a name="policy-control-overview-for-microsoft-teams"></a>Microsoft Teams のポリシー制御の概要

Microsoft では、Microsoft 365 の一部である Microsoft Teams を使用する際にデータの収集方法と使用方法を選択するのに必要な情報とコントロールを提供するように努めています。

この記事は、次の領域のプライバシー制御に関する情報を提供することを目的としています。

- **診断データ** は、組織内で Windows を実行しているコンピューターで使用されている Teams と Office ソフトウェアについての診断データを収集し、Microsoft に送信します。
- **接続エクスペリエンス**は、クラウドベースの機能を使用し、強化された Teams と Office 機能をユーザーに提供します。

これらの変更の一部として、新規および更新されたユーザー インターフェイス (UI) 要素とポリシーの設定があります。

> [!IMPORTANT]
> 詳細については、M365 の「[ポリシー管理の概要](https://docs.microsoft.com/deployoffice/privacy/overview-privacy-controls)」のコンテンツをご覧ください。

## <a name="diagnostic-data-sent-from-microsoft-365-apps-for-enterprise-to-microsoft"></a>Microsoft 365 Apps for enterprise から Microsoft に送信される診断データ

診断データは次の目的で使用されます。

- Teams を安全かつ最新の状態に保ちます。
- 問題を検出、診断、修正します。
- 製品の改善を行います。

収集されたデータの例は、次のとおりです。

- アプリケーションの言語
- ユーザーの種類
- OS のビルド バージョン

## <a name="clients-that-adhere-to-diagnostic-controls"></a>診断制御に準拠しているクライアント

次のクライアントは、診断制御に準拠してデータを送信します。

- iOS
- Android
- デスクトップ (win32 API を使用しているコンポーネントのみ)

必要なモバイル データ診断については、「[モバイルのポリシー制御診断データ](policy-control-diagnostic-data-mobile.md)」をご覧ください。

必要なデスクトップ データ診断については、「[デスクトップのポリシー制御診断データ](policy-control-diagnostic-data-desktop.md)」をご覧ください。

## <a name="diagnostic-data-sent-from-the-teams-app-to-microsoft"></a>Teams アプリから Microsoft に送信された診断データ

この、組織内の Windows を実行しているコンピューターで使用されている Teams ソフトウェアについての診断データは、収集されて Microsoft に送信されます。

Teams ソフトウェアには、選択可能な 3 つのレベルの診断データがあります。

- **必須** Office をセキュリティで保護し、最新の状態を維持し、インストールされているデバイス上で正常に動作するために必要な最小限のデータ。
- **オプション** 製品の改良に役立ち、問題の検出、診断、修正に役立つ高度な情報を提供する追加データ。
- **なし** ユーザーのデバイスで実行されている Teams ソフトウェアに関する診断データは収集されず、Microsoft に送信されません。 ただし、このオプションはユーザーが Teams を使用しているときに発生する問題を検出、診断、および修正する機能を大幅に制限します。

必須の診断データには、たとえば、デバイスにインストールされている Teams クライアントのバージョンに関する情報や、会議に参加しようとしたときに Teams アプリケーションがクラッシュすることを示す情報などがあります。 オプションの診断データには、通話の開始にかかる時間に関する情報が含まれる場合があり、接続またはネットワーク パフォーマンスの問題を示している可能性があります。

オプションの診断データを送信するよう選択した場合は、必須の診断データも含まれています。

組織の管理者は、ポリシー設定を使用して Microsoft に送信する診断データのレベルを選択できます。 設定を変更しない限り、オプションの診断データが Microsoft に送信されます。 オプションの診断データを提供することで、Microsoft の Office エンジニアリング チームは問題を検出、診断、および軽減し、組織への影響を少なくすることができます。

組織の資格情報 (仕事用アカウントまたは学校用アカウントと呼ばれることもあります) を使用して Teams にサインインした場合、ユーザーは自分のデバイスの診断データのレベルを変更できません。

この診断データには、ユーザーの名前、ユーザーの電子メール アドレス、または Office ファイルのコンテンツは含まれません。 Microsoft のシステムでは、ユーザーの診断データに関連付ける一意の ID を作成しています。 Teams アプリが 100 回クラッシュしたことを示す診断データを受信すると、この一意の ID によって、1 人のユーザーが 100 回クラッシュしたのか、100 人の異なるユーザーが 1 回ずつクラッシュしたかを判断できます。 この一意の ID を特定のユーザーの識別に使用することはありません。

## <a name="required-service-data-for-connected-experiences"></a>接続エクスペリエンスに必要なサービス データ

必要なサービス データとは、ユーザーがクラウドベースの接続エクスペリエンスを提供できるようにし、エクスペリエンスをセキュリティで保護し、期待どおりに機能するようにするためのデータです。 次の 3 つの種類の情報が、必要なサービス データを構成します。

- **お客様のコンテンツ**。Word 文書に入力したテキストなど、Office を使用して作成したコンテンツ。
- **機能データ**。アプリの構成情報など、接続エクスペリエンスがタスクを実行するために必要な情報を含みます。
- **サービス診断データ**。サービスをセキュリティで保護し、最新の状態に保ち、期待どおりに実行するために必要なデータ。 このデータは接続エクスペリエンスに厳密に関連しているため、必須またはオプションの診断データ レベルとは別になります。

この機能をユーザーに提供しないことを選択できます。その場合、この情報は、接続されたエクスペリエンスの機能をサポートするために Microsoft に提供されません。 [必要なサービス データ](https://docs.microsoft.com/deployoffice/privacy/required-service-data)の詳細を確認できます。

## <a name="essential-services-for-microsoft-teams"></a>Microsoft Teams の重要なサービス

Microsoft 365 Apps for enterprise の機能に不可欠な一連のサービスもあります。これらを無効にすることはできません。 たとえば、Microsoft 365 Apps for enterprise を使用するためのライセンスを正しく取得しているかどうかを確認するライセンス サービスです。 これらのサービスに関する必要なサービス データは、設定済みの他のポリシー設定に関係なく、収集されて Microsoft に送信されます。

詳細については、 [Office の不可欠なサービス](https://docs.microsoft.com/deployoffice/privacy/essential-services)を参照してください。
