---
title: Microsoft Teams Roomsでサポートされている条件付きアクセスとIntuneデバイス コンプライアンス ポリシー
ms.author: dstrome
author: dstrome
ms.reviewer: kspiess
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
description: Microsoft Teams Roomsでサポートされ推奨される条件付きアクセスポリシーとIntuneデバイス コンプライアンス ポリシーについて説明します。
ms.openlocfilehash: 8492f94106423498c7e301e48c8f4d046d569674
ms.sourcegitcommit: 726df9ecac561bda18e349a5adab9bc85e52844d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2022
ms.locfileid: "65761469"
---
# <a name="supported-conditional-access-and-intune-device-compliance-policies-for-microsoft-teams-rooms-and-teams-android-devices"></a>Microsoft Teams RoomsおよびTeams Android デバイスに対してサポートされている条件付きアクセスポリシーとIntuneデバイス コンプライアンス ポリシー

この記事では、Microsoft Teams Roomsでサポートされている条件付きアクセスポリシーとIntuneデバイス コンプライアンス ポリシーについて説明します。 ベスト プラクティスとポリシーの例については、「[条件付きアクセスとMicrosoft Teams RoomsのIntuneコンプライアンスのベスト プラクティス」を](conditional-access-and-compliance-for-devices.md)参照してください。

> [!NOTE]
> Teams Roomsは、条件付きアクセス ポリシーを割り当てるデバイスに既にデプロイされている必要があります。 Teams Roomsまだデプロイしていない場合は、「[会議室と共有Teamsデバイスのリソース アカウントを作成する」と「Android](with-office-365.md)[にMicrosoft Teams Roomsを展開](../devices/collab-bar-deploy.md)する」を参照してください。

## <a name="supported-conditional-access-policies"></a>サポートされている条件付きアクセス ポリシー  

次の一覧には、WindowsとAndroidのTeams Roomsと、Teams パネル、電話、ディスプレイのポリシーでサポートされている条件付きアクセス ポリシーが含まれています。

| 割り当て                               | WindowsのTeams Rooms                                                                                                                                                                              | AndroidとパネルのTeams Rooms                                                                                                                                                                              | Teams電話とディスプレイ                                                                                                                                                    |
|------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ユーザー ID またはワークロード ID              | サポート                                                                                                                                                                            | サポート                                                                                                                                                                            | サポート                                                                                                                                                            |
| クラウド アプリまたはアクション                    | サポート <br><br> Teams Roomsは、Office 365 Exchange Online、Office 365 SharePoint Online、Microsoft Teamsの 3 つのクラウド アプリTeamsモードでアクセスする必要があります。 | サポート <br><br> Teams Roomsは、Office 365 Exchange Online、Office 365 SharePoint Online、Microsoft Teamsの 3 つのクラウド アプリTeamsモードでアクセスする必要があります。 | サポート<br><br>Teams Androidデバイスは、Office 365 Exchange Online、Office 365 SharePoint Online、Microsoft Teamsの 3 つのクラウド アプリにアクセスする必要があります |
| **条件**                           | ---                                                                                                                                                                                  | ---                                                                                                                                                                                  | ---                                                                                                                                                                  |
| ユーザー リスク                                | サポート                                                                                                                                                                            | サポート                                                                                                                                                                            | サポート                                                                                                                                                            |
| サインイン リスク                             | サポート                                                                                                                                                                            | サポート                                                                                                                                                                            | サポート                                                                                                                                                            |
| デバイス プラットフォーム                         | サポート                                                                                                                                                                            | サポート                                                                                                                                                                            | サポート                                                                                                                                                            |
| Locations                                | サポート                                                                                                                                                                            | サポート                                                                                                                                                                            | サポート                                                                                                                                                            |
| クライアント アプリ                              | 非サポート                                                                                                                                                                        | 非サポート                                                                                                                                                                        | 非サポート                                                                                                                                                        |
| デバイスのフィルター                       | サポート                                                                                                                                                                            | サポート                                                                                                                                                                            | サポート                                                                                                                                                            |
| **付与**                                | ---                                                                                                                                                                                  | ---                                                                                                                                                                                  | ---                                                                                                                                                                  |
| アクセスをブロックする                             | サポート                                                                                                                                                                            | サポート                                                                                                                                                                            | サポート                                                                                                                                                            |
| アクセスを許可する                             | サポート                                                                                                                                                                            | サポート                                                                                                                                                                            |                                                                                                                                                                      |
| 多要素認証を要求する      | 非サポート                                                                                                                                                                        | 非サポート                                                                                                                                                                        | サポート                                                                                                                                                            |
| デバイスを準拠としてマークする必要がある | サポート                                                                                                                                                                            | サポート                                                                                                                                                                            | サポート                                                                                                                                                            |
| Hybrid Azure AD 参加済みデバイスが必要    | 非サポート                                                                                                                                                                        | 非サポート                                                                                                                                                                        | 非サポート                                                                                                                                                        |
| 承認済みクライアント アプリを要求する              | 非サポート                                                                                                                                                                        | 非サポート                                                                                                                                                                        | 非サポート                                                                                                                                                        |
| アプリ保護ポリシーを要求する            | 非サポート                                                                                                                                                                        | 非サポート                                                                                                                                                                        | 非サポート                                                                                                                                                        |
| パスワードの変更を要求する                  | 非サポート                                                                                                                                                                        | 非サポート                                                                                                                                                                        | 非サポート                                                                                                                                                        |

> [!NOTE]
> Skype for Business Online は廃止され、サポートされていません。 Skype for Business Online クラウド アプリは、デバイス コンプライアンス ベースの条件付きアクセス ポリシーではサポートされていません。

> [!NOTE]
> WindowsのMicrosoft Teams Roomsは、デバイス コンプライアンス付与制御をサポートするために、次の要件を満たしている必要があります。
>
> - Microsoft Teams Rooms アプリケーション 4.8.19.0 以降
> - Windows 10 バージョン 20H2 以降 (10.0.19042)

## <a name="supported-device-compliance-policies"></a>サポートされているデバイス コンプライアンス ポリシー 

AndroidのWindowsとTeams Roomsに関するMicrosoft Teams Roomsは、さまざまなデバイス コンプライアンス ポリシーをサポートします。

#### <a name="teams-rooms-on-windows"></a>[WindowsのTeams Rooms](#tab/mtr-w)

Teams Roomsで使用するためのデバイス コンプライアンス設定と推奨事項の表を次に示します。  

| ポリシー                                                                                                                      | 使用するための条件   | メモ                                                                                                                                       |
|-----------------------------------------------------------------------------------------------------------------------------|----------------|---------------------------------------------------------------------------------------------------------------------------------------------|
| [**デバイスの正常性**](/mem/intune/protect/compliance-policy-create-windows#device-health)                                     | --             | --                                                                                                                                          |
| BitLocker を要求する                                                                                                           | サポート      | Teams Roomsで最初に BitLocker を有効にした場合にのみ使用します。                                                                                |
| デバイスでセキュア ブートを有効にする必要がある                                                                             | サポート      | セキュア ブートは、Teams Roomsの要件です。                                                                                              |
| コードの整合性を要求する                                                                                                      | サポート      | コードの整合性は、既にTeams Roomsの要件です。                                                                                    |
| [**デバイスのプロパティ**](/mem/intune/protect/compliance-policy-create-windows#device-properties)                             | --             | --                                                                                                                                          |
| オペレーティング システムのバージョン (最小、最大)                                                                                 | 非サポート  | Teams Rooms新しいバージョンのWindowsに自動的に更新され、ここで値を設定すると、OS の更新後のサインインが正常に行われなくなる可能性があります。 |
| モバイル デバイスの OS バージョン (最小、最大)                                                                            | サポートされていません。 |                                                                                                                                             |
| 有効なオペレーティング システム ビルド                                                                                               | 非サポート  |                                                                                                                                             |
| [**Configuration Managerコンプライアンス**](/mem/intune/protect/compliance-policy-create-windows#device-properties)              | --             | --                                                                                                                                          |
| Configuration Managerからデバイスコンプライアンスを要求する                                                                        | サポート      |                                                                                                                                             |
| [**システム セキュリティ**](/mem/intune/protect/compliance-policy-create-windows#system-security)                                 | --             | --                                                                                                                                          |
| すべてのパスワード ポリシー                                                                                                       | 非サポート  | パスワード ポリシーを使用すると、ローカル Skype アカウントが自動的にサインインできなくなります。                                                        |
| デバイス上のデータ ストレージの暗号化が必要です。                                                                               | サポート      | Teams Roomsでデータ ストレージの暗号化を最初に有効にした場合にのみ使用します。                                                               |
| ファイアウォール                                                                                                                    | サポート      | ファイアウォールは既にTeams Roomsの要件です                                                                                           |
| トラステッド プラットフォーム モジュール (TPM)                                                                                               | サポート      | トラステッド プラットフォーム モジュール (TPM) は、既にTeams Roomsの要件です。                                                                     |
| ウイルス対策                                                                                                                   | サポート      | ウイルス対策 (Windows Defender) は既にTeams Roomsの要件です。                                                                      |
| スパイウェア 対策                                                                                                                 | サポート      | スパイウェア対策 (Windows Defender) は既にTeams Roomsの要件です。                                                                    |
| Microsoft Defender マルウェア対策                                                                                              | サポート      | Microsoft Defender マルウェア対策は、既にTeams Roomsの要件です。                                                                    |
| Microsoft Defender マルウェア対策の最小バージョン                                                                              | サポートされていません。 | Teams Roomsこのコンポーネントを自動的に更新するため、コンプライアンス ポリシーを設定する必要はありません。                                             |
| Microsoft Defender マルウェア対策セキュリティ インテリジェンスを最新の状態に                                                             | サポート      | Microsoft Defender マルウェア対策が既にTeams Roomsの要件であることを検証します。                                                      |
| リアルタイム保護                                                                                                        | サポート      | リアルタイム保護は、既にTeams Roomsの要件です。                                                                            |
| [**Microsoft Defender for Endpoint**](/mem/intune/protect/compliance-policy-create-windows#microsoft-defender-for-endpoint) | --             | --                                                                                                                                          |
| デバイスがコンピューターのリスク スコア以下である必要があります。                                                                | サポート      |                                                                                                                                             |

#### <a name="teams-rooms-on-android"></a>[AndroidのTeams Rooms](#tab/mtr-a)

Teams Roomsで使用するためのデバイス コンプライアンス設定と推奨事項の表を次に示します。  

| ポリシー                                                                                                                                  | 使用するための条件  | メモ                                                                         |
|-----------------------------------------------------------------------------------------------------------------------------------------|---------------|-------------------------------------------------------------------------------|
| [**Microsoft Defender for Endpoint**](/mem/intune/protect/compliance-policy-create-android#microsoft-defender-for-endpoint)             | --            | --                                                                            |
| デバイスがコンピューターのリスク スコアの下に存在することを要求する                                                                             | 非サポート |                                                                               |
| [**デバイスの正常性**](/mem/intune/protect/compliance-policy-create-android#device-health)                                                 | --            | --                                                                            |
| デバイス管理者が管理するデバイス                                                                                                | 必須      | デバイス管理Teams Androidデバイス管理者が有効になっている必要があります。 |
| ルート化されたデバイス                                                                                                                          | サポート     |                                                                               |
| デバイスがデバイスの脅威レベル以下である必要がある                                                                            | 非サポート |                                                                               |
| [**Google Play保護**](/mem/intune/protect/compliance-policy-create-android#device-health)                                           | --            | --                                                                            |
| Google Play 開発者サービスが構成されている                                                                                                      | 非サポート | google play は、Teams Android デバイスにインストールされていません。                         |
| 最新のセキュリティ プロバイダー                                                                                                            | 非サポート | google play は、Teams Android デバイスにインストールされていません。                         |
| アプリでの脅威スキャン                                                                                                                     | 非サポート | google play は、Teams Android デバイスにインストールされていません。                         |
| SafetyNet デバイス構成証明                                                                                                            | 非サポート | google play は、Teams Android デバイスにインストールされていません。                         |
| [**デバイスのプロパティ**](/mem/intune/protect/compliance-policy-create-android#device-properties)                                         | --            | --                                                                            |
| オペレーティング システムのバージョン (最小、最大)                                                                                             | サポート     |                                                                               |
| [**システム セキュリティ**](/mem/intune/protect/compliance-policy-create-android#system-security)                                             | --            | --                                                                            |
| デバイス上のデータ ストレージの暗号化が必要です。                                                                                           | サポート     |                                                                               |
| [**デバイスのセキュリティ**](/mem/intune/protect/compliance-policy-create-android#device-security)                                             | --            | --                                                                            |
| 不明なソースからアプリをブロックする                                                                                                         | 非サポート | Teams管理者のみがアプリまたは OEM ツールをインストールする                                   |
| アプリ ランタイムの整合性をポータル サイトする                                                                                                    | サポート     |                                                                               |
| 制限付きアプリ                                                                                                                         | 非サポート |                                                                               |
| デバイスで USB デバッグをブロックする                                                                                                           | サポート     |                                                                               |
| [**すべてのAndroid デバイス*](/mem/intune/protect/compliance-policy-create-android#all-android-devices)                                      | --            | --                                                                            |
| パスワードが必要になるまでの最大非アクティブ時間 (分)                                                                              | 非サポート |                                                                               |
| モバイル デバイスのロックを解除するためにパスワードを要求する                                                                                             | 非サポート |                                                                               |
| [**Android 10 以降**](/mem/intune/protect/compliance-policy-create-android#android-10-and-later)                                   | --            | --                                                                            |
| [**Android 9 以前または Samsung Knox**](/mem/intune/protect/compliance-policy-create-android#android-9-and-earlier-or-samsung-knox) | --            | --                                                                            |
| 必要なパスワードの種類                                                                                                                  | 非サポート |                                                                               |

#### <a name="teams-phones-and-displays"></a>[Teams電話とディスプレイ](#tab/phones)

次の表は、Teams電話とディスプレイで使用するためのデバイス コンプライアンス設定と推奨事項の表です。  

| ポリシー                                                                                                                                  | 使用するための条件  | メモ                                                                         |
|-----------------------------------------------------------------------------------------------------------------------------------------|---------------|-------------------------------------------------------------------------------|
| [**Microsoft Defender for Endpoint**](/mem/intune/protect/compliance-policy-create-android#microsoft-defender-for-endpoint)             | --            | --                                                                            |
| デバイスがコンピューターのリスク スコアの下に存在することを要求する                                                                             | 非サポート |                                                                               |
| [**デバイスの正常性**](/mem/intune/protect/compliance-policy-create-android#device-health)                                                 | --            | --                                                                            |
| デバイス管理者が管理するデバイス                                                                                                | 必須      | デバイス管理Teams Androidデバイス管理者が有効になっている必要があります。 |
| ルート化されたデバイス                                                                                                                          | サポート     |                                                                               |
| デバイスがデバイスの脅威レベル以下である必要がある                                                                            | 非サポート |                                                                               |
| [**Google Play保護**](/mem/intune/protect/compliance-policy-create-android#device-health)                                           | --            | --                                                                            |
| Google Play 開発者サービスが構成されている                                                                                                      | 非サポート | google play は、Teams Android デバイスにインストールされていません。                         |
| 最新のセキュリティ プロバイダー                                                                                                            | 非サポート | google play は、Teams Android デバイスにインストールされていません。                         |
| アプリでの脅威スキャン                                                                                                                     | 非サポート | google play は、Teams Android デバイスにインストールされていません。                         |
| SafetyNet デバイス構成証明                                                                                                            | 非サポート | google play は、Teams Android デバイスにインストールされていません。                         |
| [**デバイスのプロパティ**](/mem/intune/protect/compliance-policy-create-android#device-properties)                                         | --            | --                                                                            |
| オペレーティング システムのバージョン (最小、最大)                                                                                             | サポート     |                                                                               |
| [**システム セキュリティ**](/mem/intune/protect/compliance-policy-create-android#system-security)                                             | --            | --                                                                            |
| デバイス上のデータ ストレージの暗号化が必要です。                                                                                           | サポート     | 製造元は、Intuneが認識しない方法で、デバイスに暗号化属性を構成する場合があります。 このような場合は、デバイスを非準拠としてマークIntune。<br><br>製造元がこれらの暗号化属性を構成する方法は、デバイスのモデルによって異なる場合があります。 特定のモデルの詳細については、デバイスの製造元にお問い合わせください。 |
| [**デバイスのセキュリティ**](/mem/intune/protect/compliance-policy-create-android#device-security)                                             | --            | --                                                                            |
| 不明なソースからアプリをブロックする                                                                                                         | 非サポート | Teams管理者のみがアプリまたは OEM ツールをインストールする                                   |
| アプリ ランタイムの整合性をポータル サイトする                                                                                                    | サポート     |                                                                               |
| 制限付きアプリ                                                                                                                         | 非サポート |                                                                               |
| デバイスで USB デバッグをブロックする                                                                                                           | サポート     |                                                                               |
| [**すべてのAndroid デバイス*](/mem/intune/protect/compliance-policy-create-android#all-android-devices)                                      | --            | --                                                                            |
| パスワードが必要になるまでの最大非アクティブ時間 (分)                                                                              | 非サポート |                                                                               |
| モバイル デバイスのロックを解除するためにパスワードを要求する                                                                                             | 非サポート |                                                                               |
| [**Android 10 以降**](/mem/intune/protect/compliance-policy-create-android#android-10-and-later)                                   | --            | --                                                                            |
| [**Android 9 以前または Samsung Knox**](/mem/intune/protect/compliance-policy-create-android#android-9-and-earlier-or-samsung-knox) | --            | --                                                                            |
| 必要なパスワードの種類                                                                                                                  | 非サポート |                                                                               |



#### <a name="teams-panels"></a>[Teams パネル](#tab/panels)

Teams パネルで使用するためのデバイス コンプライアンス設定と推奨事項の表を次に示します。  

| ポリシー                                                                                                                                  | 使用するための条件  | メモ                                                                         |
|-----------------------------------------------------------------------------------------------------------------------------------------|---------------|-------------------------------------------------------------------------------|
| [**Microsoft Defender for Endpoint**](/mem/intune/protect/compliance-policy-create-android#microsoft-defender-for-endpoint)             | --            | --                                                                            |
| デバイスがコンピューターのリスク スコアの下に存在することを要求する                                                                             | 非サポート |                                                                               |
| [**デバイスの正常性**](/mem/intune/protect/compliance-policy-create-android#device-health)                                                 | --            | --                                                                            |
| デバイス管理者が管理するデバイス                                                                                                | 必須      | デバイス管理Teams Androidデバイス管理者が有効になっている必要があります。 |
| ルート化されたデバイス                                                                                                                          | サポート     |                                                                               |
| デバイスがデバイスの脅威レベル以下である必要がある                                                                            | 非サポート |                                                                               |
| [**Google Play保護**](/mem/intune/protect/compliance-policy-create-android#device-health)                                           | --            | --                                                                            |
| Google Play 開発者サービスが構成されている                                                                                                      | 非サポート | google play は、Teams Android デバイスにインストールされていません。                         |
| 最新のセキュリティ プロバイダー                                                                                                            | 非サポート | google play は、Teams Android デバイスにインストールされていません。                         |
| アプリでの脅威スキャン                                                                                                                     | 非サポート | google play は、Teams Android デバイスにインストールされていません。                         |
| SafetyNet デバイス構成証明                                                                                                            | 非サポート | google play は、Teams Android デバイスにインストールされていません。                         |
| [**デバイスのプロパティ**](/mem/intune/protect/compliance-policy-create-android#device-properties)                                         | --            | --                                                                            |
| オペレーティング システムのバージョン (最小、最大)                                                                                             | サポート     |                                                                               |
| [**システム セキュリティ**](/mem/intune/protect/compliance-policy-create-android#system-security)                                             | --            | --                                                                            |
| デバイス上のデータ ストレージの暗号化が必要です。                                                                                           | サポート     |                                                                               |
| [**デバイスのセキュリティ**](/mem/intune/protect/compliance-policy-create-android#device-security)                                             | --            | --                                                                            |
| 不明なソースからアプリをブロックする                                                                                                         | 非サポート | Teams管理者のみがアプリまたは OEM ツールをインストールする                                   |
| アプリ ランタイムの整合性をポータル サイトする                                                                                                    | サポート     |                                                                               |
| 制限付きアプリ                                                                                                                         | 非サポート |                                                                               |
| デバイスで USB デバッグをブロックする                                                                                                           | サポート     |                                                                               |
| [**すべてのAndroid デバイス*](/mem/intune/protect/compliance-policy-create-android#all-android-devices)                                      | --            | --                                                                            |
| パスワードが必要になるまでの最大非アクティブ時間 (分)                                                                              | 非サポート |                                                                               |
| モバイル デバイスのロックを解除するためにパスワードを要求する                                                                                             | 非サポート |                                                                               |
| [**Android 10 以降**](/mem/intune/protect/compliance-policy-create-android#android-10-and-later)                                   | --            | --                                                                            |
| [**Android 9 以前または Samsung Knox**](/mem/intune/protect/compliance-policy-create-android#android-9-and-earlier-or-samsung-knox) | --            | --                                                                            |
| 必要なパスワードの種類                                                                                                                  | 非サポート |                                                                               |

---
