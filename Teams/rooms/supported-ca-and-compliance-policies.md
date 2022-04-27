---
title: Microsoft Teams Roomsでサポートされている条件付きアクセスとIntuneデバイス コンプライアンス ポリシー
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
description: Microsoft Teams Roomsでサポートされ推奨される条件付きアクセスポリシーとIntuneデバイス コンプライアンス ポリシーについて説明します。
ms.openlocfilehash: 19e4593a6135c79eb156a1b34847ab518d6e8ea4
ms.sourcegitcommit: bd05783dfb33a63e0eb083a2135f97d110dc81a3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2022
ms.locfileid: "65059238"
---
# <a name="supported-conditional-access-and-intune-device-compliance-policies-for-microsoft-teams-rooms"></a>Microsoft Teams Roomsでサポートされている条件付きアクセスとIntuneデバイス コンプライアンス ポリシー

この記事では、Microsoft Teams Roomsでサポートされている条件付きアクセスポリシーとIntuneデバイス コンプライアンス ポリシーについて説明します。 ベスト プラクティスとポリシーの例については、「[条件付きアクセスとMicrosoft Teams RoomsのIntuneコンプライアンスのベスト プラクティス」を](conditional-access-and-compliance-for-devices.md)参照してください。

> [!NOTE]
> Teams Roomsは、条件付きアクセス ポリシーを割り当てるデバイスに既にデプロイされている必要があります。 Teams Roomsまだデプロイしていない場合は、「[会議室と共有Teamsデバイスのリソース アカウントを作成](with-office-365.md)する」と [Android でのMicrosoft Teams Roomsのデプロイ](../devices/collab-bar-deploy.md)に関するページを参照してください。

## <a name="supported-conditional-access-policies"></a>サポートされている条件付きアクセス ポリシー  

次の一覧には、Windowsおよび Android でサポートされているTeams Roomsの条件付きアクセス ポリシーが含まれています。 

> [!NOTE]
> サポートされている Android ポリシーは、Andourd のTeams Rooms、共通エリアフォン、パネルなど、共有スペース内のすべての Android デバイスに適用されます。

| 割り当て | Windows | Android |
|------------|---------|---------|
| ユーザー ID またはワークロード ID |サポート | サポート |
|クラウド アプリまたはアクション | サポート <br><br> Teams Roomsは、Office 365 Exchange Online、Office 365 SharePoint Online、Microsoft Teamsの 3 つのクラウド アプリTeamsモードでアクセスする必要があります。 | サポート <br><br> Teams Roomsは、Office 365 Exchange Online、Office 365 SharePoint Online、Microsoft Teamsの 3 つのクラウド アプリTeamsモードでアクセスする必要があります。 |
|**条件**| --- | --- |
| ユーザー リスク | サポート | サポート |
| サインイン リスク | サポート | サポート |
| デバイス プラットフォーム | サポート | サポート |
| Locations | サポート | サポート |
|クライアント アプリ |非サポート| 非サポート |
|デバイスのフィルター | サポート | サポート |
|**付与**| --- | --- |
| アクセスをブロックする | サポート | サポート |
| アクセスを許可する | サポート | サポート | 
| 多要素認証を要求する | 非サポート | 非サポート |
| デバイスを準拠としてマークする必要がある | サポート | サポート |
|ハイブリッド Azure AD参加しているデバイスを必要とする | 非サポート | 非サポート |
|承認済みクライアント アプリを要求する | 非サポート | 非サポート |
| アプリ保護ポリシーを要求する | 非サポート |非サポート |
| パスワードの変更を要求する | 非サポート | 非サポート |

> [!NOTE]
> Skype for Business Online は廃止され、サポートされていません。 Skype for Business Online クラウド アプリは、デバイス コンプライアンス ベースの条件付きアクセス ポリシーではサポートされていません。

> [!NOTE]
> WindowsのMicrosoft Teams Roomsは、デバイス コンプライアンス付与制御をサポートするために、次の要件を満たしている必要があります。
>
> - Microsoft Teams Rooms アプリケーション 4.8.19.0 以降
> - Windows 10 バージョン 20H2 以降 (10.0.19042)

## <a name="supported-device-compliance-policies"></a>サポートされているデバイス コンプライアンス ポリシー 

Android のWindowsとTeams Roomsに関するMicrosoft Teams Roomsでは、さまざまなデバイス コンプライアンス ポリシーがサポートされています。

#### <a name="teams-rooms-on-windows"></a>[WindowsのTeams Rooms](#tab/mtr-w)

Teams Roomsで使用するためのデバイス コンプライアンス設定と推奨事項の表を次に示します。  

|ポリシー | 使用するための条件 | メモ|
|---------|-------------|-------|
| [**デバイスの正常性**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22device-health) | -- | -- |
|BitLocker を要求する| サポート | Teams Roomsで最初に BitLocker を有効にした場合にのみ使用します。 |
|デバイスでセキュア ブートを有効にする必要がある |サポート |セキュア ブートは、Teams Roomsの要件です。 |
|コードの整合性を要求する |サポート  | コードの整合性は、既にTeams Roomsの要件です。 |
| [**デバイスのプロパティ**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22device-properties) | -- | -- |
|オペレーティング システムのバージョン (最小、最大) |非サポート | Teams Rooms新しいバージョンのWindowsに自動的に更新され、ここで値を設定すると、OS の更新後のサインインが正常に行われなくなる可能性があります。|
|モバイル デバイスの OS バージョン (最小、最大) | サポートされていません。 | 該当なし |
| 有効なオペレーティング システム ビルド | 非サポート | 該当なし |
| [**Configuration Managerコンプライアンス**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22device-properties) | -- | -- |
| Configuration Managerからデバイスコンプライアンスを要求する | サポート |  該当なし |
| [**システム セキュリティ**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22system-security) | -- | -- |
| すべてのパスワード ポリシー | 非サポート | パスワード ポリシーを使用すると、ローカル Skype アカウントが自動的にサインインできなくなります。 |
| デバイス上のデータ ストレージの暗号化が必要です。 | サポート  | Teams Roomsでデータ ストレージの暗号化を最初に有効にした場合にのみ使用します。 |
| ファイアウォール | サポート | ファイアウォールは既にTeams Roomsの要件です |
| トラステッド プラットフォーム モジュール (TPM) | サポート | トラステッド プラットフォーム モジュール (TPM) は、既にTeams Roomsの要件です。 |
| ウイルス対策 | サポート | ウイルス対策 (Windows Defender) は既にTeams Roomsの要件です。 |
| スパイウェア 対策 | サポート | スパイウェア対策 (Windows Defender) は既にTeams Roomsの要件です。 |
| Microsoft Defender マルウェア対策 | サポート | Microsoft Defender マルウェア対策は、既にTeams Roomsの要件です。 |
| Microsoft Defender マルウェア対策の最小バージョン | サポートされていません。 | Teams Roomsこのコンポーネントを自動的に更新するため、コンプライアンス ポリシーを設定する必要はありません。|
| Microsoft Defender マルウェア対策セキュリティ インテリジェンス
最新 | サポート | Microsoft Defender マルウェア対策が既にTeams Roomsの要件であることを検証します。 |
| リアルタイム保護 | サポート | リアルタイム保護は、既にTeams Roomsの要件です。 |
| [**Microsoft Defender for Endpoint**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22microsoft-defender-for-endpointws) | -- | -- |
| デバイスがコンピューターのリスク スコア以下である必要があります。 | サポート |  該当なし |

#### <a name="teams-rooms-on-android"></a>[Android でのTeams Rooms](#tab/mtr-a)

Teams Roomsで使用するためのデバイス コンプライアンス設定と推奨事項の表を次に示します。  

| ポリシー | 使用するための条件 | メモ |
|---------|-------------|-------|
| [**Microsoft Defender for Endpoint**](/mem/intune/protect/compliance-policy-create-android#microsoft-defender-for-endpoint) | -- | -- |
| デバイスがコンピューターのリスク スコアの下に存在することを要求する | 非サポート |  該当なし |
| [**デバイスの正常性**](/mem/intune/protect/compliance-policy-create-android%22%20/l%20%22device-health) | -- | -- |
| デバイス管理者が管理するデバイス | 必須 | Android デバイス管理Teams、デバイス管理者を有効にする必要があります。 |
| ルート化されたデバイス | サポート |  該当なし |
| デバイスがデバイスの脅威レベル以下である必要がある | 非サポート |  該当なし |
| [**Google Play Protect**](/mem/intune/protect/compliance-policy-create-android#device-health) | -- | -- |
| Google Play Services が構成されている | 非サポート | Teams Android デバイスに Google Play がインストールされていません。 |
| 最新のセキュリティ プロバイダー | 非サポート | Teams Android デバイスに Google Play がインストールされていません。 |
| アプリでの脅威スキャン | 非サポート | Teams Android デバイスに Google Play がインストールされていません。 |
| SafetyNet デバイス構成証明 | 非サポート | Teams Android デバイスに Google Play がインストールされていません。|
| [**デバイスのプロパティ**](/mem/intune/protect/compliance-policy-create-android#device-properties) | -- | -- |
| オペレーティング システムのバージョン (最小、最大) | サポート |  該当なし |
[**システム セキュリティ**](/mem/intune/protect/compliance-policy-create-android#system-security) | -- | -- |
| デバイス上のデータ ストレージの暗号化が必要です。 |サポート |  該当なし |
[**デバイスのセキュリティ**](/mem/intune/protect/compliance-policy-create-android#device-security) | -- | -- |
| 不明なソースからアプリをブロックする | 非サポート | Teams管理者のみがアプリまたは OEM ツールをインストールする |
| アプリ ランタイムの整合性をポータル サイトする | サポート |  該当なし|
| 制限付きアプリ | 非サポート |  該当なし |
| デバイスで USB デバッグをブロックする | サポート |  該当なし|
[**すべての Android デバイス*](/mem/intune/protect/compliance-policy-create-android#all-android-devices) | -- | -- |
|パスワードが必要になるまでの最大非アクティブ時間 (分) | 非サポート |  該当なし |
| モバイル デバイスのロックを解除するためにパスワードを要求する | 非サポート | 該当なし |
| [**Android 10 以降**](/mem/intune/protect/compliance-policy-create-android#android-10-and-later) | -- | -- |
| [**Android 9 以前または Samsung Knox**](/mem/intune/protect/compliance-policy-create-android#android-9-and-earlier-or-samsung-knox) | -- | -- |
|必要なパスワードの種類 |非サポート | 該当なし|

---
