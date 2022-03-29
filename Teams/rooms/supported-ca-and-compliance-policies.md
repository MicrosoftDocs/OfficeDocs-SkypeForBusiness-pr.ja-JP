---
title: Microsoft Teams Rooms でサポートされている条件付きアクセスポリシーと Intune デバイス コンプライアンス ポリシー
ms.author: czawideh
author: cazawideh
ms.reviewer: kspiess
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
description: Microsoft Teams Rooms でサポートおよび推奨される条件付きアクセスポリシーと Intune デバイス コンプライアンス ポリシーについてMicrosoft Teamsします。
ms.openlocfilehash: ea27f71a7d4f64bc1d9e8c8a3cd3d7b2a52151f3
ms.sourcegitcommit: ecc67b7b9378cc72f85517f30c32680045056fda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2022
ms.locfileid: "64504197"
---
# <a name="supported-conditional-access-and-intune-device-compliance-policies-for-microsoft-teams-rooms"></a>Microsoft Teams Rooms でサポートされている条件付きアクセスポリシーと Intune デバイス コンプライアンス ポリシー

この記事では、Microsoft Teams Rooms でサポートされている条件付きアクセスポリシーと Intune デバイス コンプライアンス ポリシーについて説明します。 ベスト プラクティスとポリシーの例については、「Microsoft Teams [Rooms の条件付きアクセスと Intune コンプライアンスのベスト プラクティス」を参照してください](conditional-access-and-compliance-for-devices.md)。

> [!NOTE]
> Teamsアクセス ポリシーを割り当てるデバイスに会議室が既にデプロイされている必要があります。 Teams 会議室をまだデプロイしていない場合は、「会議室と共有 [Teams](with-office-365.md) デバイスのリソース アカウントを作成する」と「[Android で Microsoft Teams 会議室](../devices/collab-bar-deploy.md)をデプロイする」を参照してください。

## <a name="supported-conditional-access-policies"></a>サポートされている条件付きアクセス ポリシー  

次の一覧には、Teams および Android 上の Windows条件付きアクセス ポリシーが含まれています。 サポートされている Android ポリシーは、すべての Android デバイス、スマートフォン、パネルに適用されます。

| 割り当て | Windows | Android |
|------------|---------|---------|
| ユーザー ID またはワークロード ID |サポート | サポート |
|クラウド アプリまたはアクション | サポート <br><br> Teams ルームは、Teams モードの場合、Office 365 Exchange Online、Office 365 SharePoint Online、および Microsoft Teams | サポート <br><br> Teams ルームは、Teams モードの場合、Office 365 Exchange Online、Office 365 SharePoint Online、および Microsoft Teams |
|**条件**| --- | --- |
| ユーザーリスク | サポート | サポート |
| サインイン リスク | サポート | サポート |
| デバイス プラットフォーム | サポート | サポート |
| Locations | サポート | サポート |
|クライアント アプリ |非サポート| 非サポート |
|デバイスのフィルター処理 | サポート | サポート |
|**Grant**| --- | --- |
| アクセスをブロックする | サポート | サポート |
| アクセス権を付与する | サポート | サポート | 
| 多要素認証を要求する | 非サポート | 非サポート |
| デバイスを準拠としてマークする必要がある | サポート | サポート |
|参加しているデバイスAzure ADハイブリッドを要求する | 非サポート | 非サポート |
|承認されたクライアント アプリを要求する | 非サポート | 非サポート |
| アプリ保護ポリシーを要求する | 非サポート |非サポート |
| パスワードの変更を要求する | 非サポート | 非サポート |

> [!NOTE]
> Skype for Business Online は廃止され、サポートされていません。 Skype for Business Online クラウド アプリは、デバイス コンプライアンス ベースの条件付きアクセス ポリシーではサポートされていません。

> [!NOTE]
> Microsoft Teamsの会議室Windows、デバイス コンプライアンス付与コントロールをサポートするには、次の要件を満たす必要があります。
>
> - Microsoft Teams Rooms アプリケーション 4.8.19.0 以上
> - Windows 10 20H2 以上 (10.0.19042)

## <a name="supported-device-compliance-policies"></a>サポートされているデバイス コンプライアンス ポリシー 

Microsoft Teams Windows Rooms on Android Teams Rooms では、さまざまなデバイス コンプライアンス ポリシーがサポートされています。

#### <a name="teams-rooms-on-windows"></a>[Teamsの会議室Windows](#tab/mtr-w)

次の表は、デバイスのコンプライアンス設定と、Teams Rooms での使用に関する推奨事項を示しています。  

|ポリシー | 使用するための条件 | メモ|
|---------|-------------|-------|
| [**デバイスの正常性**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22device-health) | -- | -- |
|BitLocker が必要| サポート | 最初に会議室で BitLocker を有効にした場合Teams使用します。 |
|デバイスで Secure Boot を有効にする必要がある |サポート |セキュリティで保護されたブートは、会議室Teamsです。 |
|コード整合性を要求する |サポート  | コードの整合性は、Teamsです。 |
| [**デバイスのプロパティ**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22device-properties) | -- | -- |
|オペレーティング システムのバージョン (最小、最大) |非サポート | Teams会議室は、新しいバージョンの Windowsに自動的に更新され、ここで値を設定すると、OS の更新後に正常にサインインする可能性があります。|
|モバイル デバイスの OS バージョン (最小、最大) | サポートされていません。 | 該当なし |
| 有効なオペレーティング システム ビルド | 非サポート | 該当なし |
| [**Configuration Manager のコンプライアンス**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22device-properties) | -- | -- |
| Configuration Manager からデバイスのコンプライアンスを要求する | サポート |  該当なし |
| [**システムのセキュリティ**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22system-security) | -- | -- |
| すべてのパスワード ポリシー | 非サポート | パスワード ポリシーを使用すると、ローカル アカウントSkype自動的にサインインできません。 |
| デバイス上のデータ ストレージの暗号化が必要です。 | サポート  | Teams Rooms で最初にデータ ストレージの暗号化を有効にした場合にのみ使用します。 |
| ファイアウォール | サポート | ファイアウォールは、Teams 会議室の要件です |
| トラステッド プラットフォーム モジュール (TPM) | サポート | トラステッド プラットフォーム モジュール (TPM) は、Teamsです。 |
| ウイルス対策 | サポート | ウイルス対策 (Windows Defender) は、Teams です。 |
| Antispyware | サポート | マルウェア対策 (Windows Defender) は、Teams です。 |
| Microsoft Defender マルウェア対策 | サポート | Microsoft Defender マルウェア対策は、Teamsです。 |
| Microsoft Defender マルウェア対策の最小バージョン | サポートされていません。 | Teams、このコンポーネントは自動的に更新され、コンプライアンス ポリシーを設定する必要はありません。|
| Microsoft Defender マルウェア対策のセキュリティ インテリジェンス
最新 | サポート | Microsoft Defender マルウェア対策が既に会議室の要件Teamsします。 |
| リアルタイム保護 | サポート | リアルタイム保護は、会議室のTeamsです。 |
| [**エンドポイント用 Microsoft Defender**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22microsoft-defender-for-endpointws) | -- | -- |
| デバイスがマシンのリスク スコア以下である必要があります。 | サポート |  該当なし |

#### <a name="teams-rooms-on-android"></a>[Teams Android の会議室](#tab/mtr-a)

次の表は、デバイスのコンプライアンス設定と、Teams Rooms での使用に関する推奨事項を示しています。  

| ポリシー | 使用するための条件 | メモ |
|---------|-------------|-------|
| [**エンドポイント用 Microsoft Defender**](/mem/intune/protect/compliance-policy-create-android#microsoft-defender-for-endpoint) | -- | -- |
| デバイスがマシンのリスク スコア以下である必要がある | 非サポート |  該当なし |
| [**Device Health**](/mem/intune/protect/compliance-policy-create-android%22%20/l%20%22device-health) | -- | -- |
| デバイス管理者が管理するデバイス | サポートされていません。 | Teams Android デバイスはデバイスで管理される
管理者。 |
| ルートデバイス | サポート |  該当なし |
| デバイスがデバイスの脅威レベル以下である必要がある | 非サポート |  該当なし |
| [**Google Play Protect**](/mem/intune/protect/compliance-policy-create-android#device-health) | -- | -- |
| Google Play Services が構成されている | 非サポート | Google Play は、Android デバイスTeamsインストールされていません。 |
| 最新のセキュリティ プロバイダー | 非サポート | Google Play は、Android デバイスTeamsインストールされていません。 |
| アプリでの脅威スキャン | 非サポート | Google Play は、Android デバイスTeamsインストールされていません。 |
| SafetyNet デバイス構成証明 | 非サポート | Google Play は、Android デバイスTeamsインストールされていません。|
| [**デバイスのプロパティ**](/mem/intune/protect/compliance-policy-create-android#device-properties) | -- | -- |
| オペレーティング システムのバージョン (最小、最大) | サポート |  該当なし |
[**システムのセキュリティ**](/mem/intune/protect/compliance-policy-create-android#system-security) | -- | -- |
| デバイス上のデータ ストレージの暗号化が必要です。 |サポート |  該当なし |
[**デバイスのセキュリティ**](/mem/intune/protect/compliance-policy-create-android#device-security) | -- | -- |
| 不明なソースからアプリをブロックする | 非サポート | アプリTeams OEM ツールをインストールする管理者のみ |
| ポータル サイトランタイムの整合性 | サポート |  該当なし|
| 制限付きアプリ | 非サポート |  該当なし |
| デバイスで USB デバッグをブロックする | サポート |  該当なし|
[**すべての Android デバイス*](/mem/intune/protect/compliance-policy-create-android#all-android-devices) | -- | -- |
|パスワードが必要になる前の非アクティブ状態の最大時間 (分) | 非サポート |  該当なし |
| モバイル デバイスのロックを解除するためにパスワードを要求する | 非サポート | 該当なし |
| [**Android 10 以降**](/mem/intune/protect/compliance-policy-create-android#android-10-and-later) | -- | -- |
| [**Android 9 以前または Samsung Knox**](/mem/intune/protect/compliance-policy-create-android#android-9-and-earlier-or-samsung-knox) | -- | -- |
|必須のパスワードの種類 |非サポート | 該当なし|

---
