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
ms.openlocfilehash: 7f642b1ce9a767c30077374aa193355edbbbef09
ms.sourcegitcommit: 2591c96d8613660220c5af71fc945e27b31175d7
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2021
ms.locfileid: "52863218"
---
# <a name="policy-control-overview-for-microsoft-teams"></a>Microsoft Teams のポリシー制御の概要

Microsoft では、Microsoft 365 の一部である Microsoft Teams を使用する際にデータの収集方法と使用方法を選択するのに必要な情報とコントロールを提供するように努めています。

この記事は、次の領域のプライバシー制御に関する情報を提供することを目的としています。

- **診断データ** は、組織内で Windows を実行しているコンピューターで使用されている Teams と Office ソフトウェアについての診断データを収集し、Microsoft に送信します。
- **接続エクスペリエンス** は、クラウドベースの機能を使用し、強化された Teams と Office 機能をユーザーに提供します。

これらの変更の一部として、新規および更新されたユーザー インターフェイス (UI) 要素とポリシーの設定があります。

> [!IMPORTANT]
> 詳細については、Microsoft 365 の「[ポリシー管理の概要](/deployoffice/privacy/overview-privacy-controls)」のコンテンツをご覧ください。

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

必須の診断データ イベントとプロパティの一覧を表示するには、次の記事をご覧ください。

- [Microsoft Teams 必須モバイル診断データ](policy-control-diagnostic-data-mobile.md)
- [Microsoft Teams 必須デスクトップ診断データ](policy-control-diagnostic-data-desktop.md)

## <a name="diagnostic-data-sent-from-the-teams-app-to-microsoft"></a>Teams アプリから Microsoft に送信された診断データ

この、組織内の Windows を実行しているコンピューターで使用されている Teams ソフトウェアについての診断データは、収集されて Microsoft に送信されます。

Teams ソフトウェアには、選択可能な 3 つのレベルの診断データがあります。

- **必須** Office をセキュリティで保護し、最新の状態を維持し、インストールされているデバイス上で正常に動作するために必要な最小限のデータ。
- **オプション** 製品の改良に役立ち、問題の検出、診断、修正に役立つ高度な情報を提供する追加データ。
- **なし** ユーザーのデバイスで実行されている Teams ソフトウェアに関する診断データは収集されず、Microsoft に送信されません。 ただし、このオプションはユーザーが Teams を使用しているときに発生する問題を検出、診断、および修正する機能を大幅に制限します。

必須の診断データには、たとえば、デバイスにインストールされている Teams クライアントのバージョンに関する情報や、会議に参加しようとしたときに Teams アプリケーションがクラッシュすることを示す情報などがあります。 オプションの診断データには、通話の開始にかかる時間に関する情報が含まれる場合があり、接続またはネットワーク パフォーマンスの問題を示している可能性があります。

オプションの診断データを送信するよう選択した場合は、必須の診断データも含まれています。

組織の管理者は、ポリシー設定を使用して Microsoft に送信する診断データのレベルを選択できます。 設定を変更しない限り、オプションの診断データが Microsoft に送信されます。 オプションの診断データを提供することで、Microsoft の Office エンジニアリング チームは問題を検出、診断、および軽減し、組織への影響を少なくすることができます。 

送信される診断データのレベルを選択するには、[Office クラウド ポリシー サービス](/deployoffice/overview-office-cloud-policy-service)を使用して、*Office から Microsoft に送信されるクライアント ソフトウェア診断データのレベルを設定する* ポリシー設定を構成します。 これは、Microsoft 365 Apps for Enterprise に付属するその他の Office アプリ (Word、Excel、PowerPoint など) で、どのレベルの診断データを送信するかを構成するために使用されるポリシー設定と同じものです。

組織の資格情報 (仕事用アカウントまたは学校用アカウントと呼ばれることもあります) を使用して Teams にサインインした場合、ユーザーは自分のデバイスの診断データのレベルを変更できません。

この診断データには、ユーザーの名前、メール アドレス、その他のユーザー コンテンツ (Teams で共有された Office ファイル、Teams 内で送信されたチャット メッセージ、Teams 内のチャネルで公開された投稿文など) は含まれません。 Microsoft のシステムでは、ユーザーの診断データに関連付ける一意の ID を作成しています。 Teams アプリが 100 回クラッシュしたことを示す診断データを受信すると、この一意の ID によって、1 人のユーザーが 100 回クラッシュしたのか、100 人の異なるユーザーが 1 回ずつクラッシュしたかを判断できます。 この一意の ID を特定のユーザーの識別に使用することはありません。

どの診断データがMicrosoftに送信されているかを確認するには、Diagnostic Data Viewerを使用できます。このビューアは、Microsoft Store から無料でダウンロードしてインストールできます。 詳細については、「[Office で診断データ ビューアーを使用する](https://support.microsoft.com/topic/cf761ce9-d805-4c60-a339-4e07f3182855)」を参照してください。

> [!NOTE]
> 診断データ ビューアーのサポートは、Android を実行するデバイスの Teams で利用可能です。 Windows、macOS、iOS を搭載したデバイスでの Teams のサポートは処理中です。

## <a name="required-service-data-for-connected-experiences"></a>接続エクスペリエンスに必要なサービス データ

必要なサービス データとは、ユーザーがクラウドベースの接続エクスペリエンスを提供できるようにし、エクスペリエンスをセキュリティで保護し、期待どおりに機能するようにするためのデータです。 この機能をユーザーに提供しないことを選択できます。その場合、この情報は、接続されたエクスペリエンスの機能をサポートするために Microsoft に提供されません。 [必要なサービス データ](/deployoffice/privacy/required-service-data)の詳細を確認できます。

## <a name="essential-services-for-microsoft-teams"></a>Microsoft Teams の重要なサービス

Microsoft 365 Apps for enterprise の機能に不可欠な一連のサービスもあります。これらを無効にすることはできません。 たとえば、Microsoft 365 Apps for enterprise を使用するためのライセンスを正しく取得しているかどうかを確認するライセンス サービスです。 これらのサービスに関する必要なサービス データは、設定済みの他のポリシー設定に関係なく、収集されて Microsoft に送信されます。

詳細については、 [Office の不可欠なサービス](/deployoffice/privacy/essential-services)を参照してください。