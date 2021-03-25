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
description: AppLocker アプリケーション制御ポリシーを使用して Teams デスクトップ クライアント アプリケーションを有効にする方法について説明します。
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
# <a name="applocker-application-control-policies-in-microsoft-teams"></a>Microsoft Teams の AppLocker アプリケーション制御ポリシー

この記事では、AppLocker アプリケーション制御ポリシーを使用して Teams デスクトップ クライアント アプリを有効にする方法について説明します。 AppLocker の使用は、管理者以外のユーザーによるプログラムとスクリプトの実行を制限するように設計されています。 AppLocker の詳細とガイダンスについては [、「AppLocker とは何ですか?」を参照してください](/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker)。

AppLocker で Teams を有効にするプロセスには、AppLocker ベースの許可リスト ポリシーの作成が必要です。 ポリシーは、グループ ポリシー管理ソフトウェア、および AppLocker の Windows PowerShell コマンドレットの使用 (詳細については [AppLocker](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference) のテクニカル リファレンスを参照) で作成されます。 AppLocker ポリシーは XML 形式で保存され、任意のテキストまたは XML エディターで編集できます。

## <a name="teams-allow-list-with-applocker"></a>AppLocker を使用した Teams の許可リスト

AppLocker ルールは、ルールのコレクションに編成されます。 AppLocker ルールは対象のアプリに適用され、これらは AppLocker ポリシーを構成するコンポーネントです。  

Teams を許可するには、すべての Teams[](/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker)アプリ ファイルがデジタル署名された状態で発行元の条件ルールを使用することをお勧めします。
  
Teams のインストール ディレクトリはユーザーが書き込み可能なので、パス ルールの使用はお勧めしません。 また、Teams クライアント アプリが更新されるごとにルールを更新する必要があるため、ハッシュ ルールの使用はお勧めしません。

Teams デスクトップ実行可能ファイルはデジタル署名付きであるから、発行元の条件は、デジタル署名と埋め込みバージョン属性に基づいてアプリ ファイルを識別します。 デジタル署名には、アプリ ファイル (発行元) を作成した会社に関する情報が含まれている。 バイナリ リソースから取得されるバージョン情報には、ファイルが含まれる製品の名前とアプリケーション ファイルのバージョン番号が含まれます。

### <a name="example-of-publisher-condition-rules"></a>発行元の条件ルールの例

Teams クライアント アプリ (すべてのファイル、すべてのバージョン) の場合は、DLL ルールの実行可能ルールに次&追加します。

```console
Publisher: O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US
Product name: MICROSOFT TEAMS
Product name: MICROSOFT TEAMS UPDATE
```

## <a name="related-topics"></a>関連項目
[AppLocker とは](/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker) 
[AppLocker のテクニカル リファレンス](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)