---
title: AppLocker コントロール ポリシー
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: rafarhi
search.appverid: MET150
f1.keywords:
- NOCSH
description: AppLocker アプリケーション制御ポリシーを使用Teamsデスクトップ クライアント アプリケーションを有効にする方法について説明します。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d6e6040956ba5e5469076b4fbbab337f58268c68
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120849"
---
# <a name="applocker-application-control-policies-in-microsoft-teams"></a>AppLocker アプリケーション制御ポリシー (Microsoft Teams

この記事では、AppLocker アプリケーション制御ポリシーをTeamsデスクトップ クライアント アプリを有効にする方法について説明します。 AppLocker の使用は、管理者以外のユーザーによるプログラムとスクリプトの実行を制限するように設計されています。 AppLocker の詳細とガイダンスについては、「AppLocker とは [」を参照してください](/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker)。

AppLocker を使用してTeamsするには、AppLocker ベースの許可リストポリシーを作成する必要があります。 ポリシーは、AppLocker のグループ ポリシー管理ソフトウェアや Windows PowerShell コマンドレットを使用して作成されます (詳細については[、AppLocker](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)のテクニカル リファレンスを参照してください)。 AppLocker ポリシーは XML 形式で保存され、任意のテキストエディターまたは XML エディターで編集できます。

## <a name="teams-allow-list-with-applocker"></a>appLocker Teams許可リストを作成する

AppLocker ルールは、ルールのコレクションに編成されます。 AppLocker ルールは対象のアプリに適用され、AppLocker ポリシーを構成するコンポーネントです。  

アプリ ファイルTeams、すべてのアプリ ファイルがデジタル署名Teams[](/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker)条件ルールを使用することをお勧めします。
  
インストール ディレクトリはユーザーが書き込み可能なので、パスTeams使用はお勧めしません。 また、クライアント アプリが更新されるごとにルールを更新する必要Teamsハッシュ 規則の使用はお勧めしません。

デスクトップTeamsファイルがデジタル署名されている場合、発行元の条件はデジタル署名と埋め込みバージョン属性に基づいてアプリ ファイルを識別します。 デジタル署名には、アプリ ファイル (発行元) を作成した会社に関する情報が含まれている。 バイナリ リソースから取得されるバージョン情報には、ファイルが含まれる製品の名前とアプリケーション ファイルのバージョン番号が含まれます。

### <a name="example-of-publisher-condition-rules"></a>発行元の条件ルールの例

新しいTeams クライアント アプリ (すべてのファイル、すべてのバージョン) で、次のコードを DLL ルールの実行可能&追加します。

```console
Publisher: O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US
Product name: MICROSOFT TEAMS
Product name: MICROSOFT TEAMS UPDATE
```

## <a name="related-topics"></a>関連トピック
[AppLocker とは](/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker) 
[AppLocker のテクニカル リファレンス](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)