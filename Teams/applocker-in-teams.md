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
description: AppLocker アプリケーション制御ポリシーを使用してTeamsデスクトップ クライアント アプリケーションを有効にする方法について説明します。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b68d698ffcb703e70e12f3801ff70fb0719bb17cb09e23facf47121529a86b0b
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54288445"
---
# <a name="applocker-application-control-policies-in-microsoft-teams"></a>Microsoft Teamsの AppLocker アプリケーション制御ポリシー

この記事では、AppLocker アプリケーション制御ポリシーでTeamsデスクトップ クライアント アプリを有効にする方法について説明します。 AppLocker の使用は、管理者以外のユーザーによるプログラムとスクリプトの実行を制限するように設計されています。 AppLocker の詳細とガイダンスについては、「 [AppLocker とは」を](/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker)参照してください。

AppLocker でTeamsを有効にするプロセスでは、AppLocker ベースの許可リスト ポリシーを作成する必要があります。 ポリシーは、グループ ポリシー管理ソフトウェアまたは AppLocker 用のWindows PowerShellコマンドレットを使用して作成されます (詳細については、[AppLocker のテクニカル リファレンス](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)を参照してください)。 AppLocker ポリシーは XML 形式で保存され、任意のテキスト エディターまたは XML エディターで編集できます。

## <a name="teams-allow-list-with-applocker"></a>AppLocker で許可リストをTeamsする

AppLocker ルールは、ルールのコレクションにまとめられます。 AppLocker ルールは対象のアプリに適用され、AppLocker ポリシーを構成するコンポーネントです。  

Teamsを許可するには、すべてのTeamsアプリ ファイルがデジタル署名されるため、[発行元の条件規則](/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker)を使用することをお勧めします。
  
Teams インストール ディレクトリはユーザーが書き込み可能であるため、パス規則の使用はお勧めしません。 また、Teams クライアント アプリが更新されるたびにルールを更新する必要があるため、ハッシュ ルールの使用はお勧めしません。

デスクトップ実行可能ファイルTeamsデジタル署名されるため、発行元の条件は、デジタル署名と埋め込みバージョンの属性に基づいてアプリ ファイルを識別します。 デジタル署名には、アプリ ファイル (発行元) を作成した会社に関する情報が含まれています。 バイナリ リソースから取得されるバージョン情報には、ファイルの一部である製品の名前と、アプリケーション ファイルのバージョン番号が含まれます。

### <a name="example-of-publisher-condition-rules"></a>発行元の条件ルールの例

Teams クライアント アプリ (すべてのファイル、すべてのバージョン) の場合は、実行可能規則& DLL 規則に次を追加します。

```console
Publisher: O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US
Product name: MICROSOFT TEAMS
Product name: MICROSOFT TEAMS UPDATE
```

## <a name="related-topics"></a>関連項目
[AppLocker](/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker)
 とは[AppLocker テクニカル リファレンス](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)