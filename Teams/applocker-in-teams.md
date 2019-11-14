---
title: Microsoft Teams の AppLocker アプリケーション制御ポリシー
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: rafarhi
search.appverid: MET150
description: AppLocker アプリケーション制御ポリシーを使って Teams デスクトップクライアントアプリケーションを有効にする方法について説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6035341aa649e966f15be7d33894f450ec8be251
ms.sourcegitcommit: b1bf37a96a8faa169d8a32b7478f1e2d1022ebbb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2019
ms.locfileid: "38311252"
---
# <a name="applocker-application-control-policies-in-microsoft-teams"></a>Microsoft Teams の AppLocker アプリケーション制御ポリシー

この記事では、AppLocker アプリケーション制御ポリシーを使って Teams デスクトップクライアントアプリを有効にする方法について説明します。 AppLocker の使用は、管理者以外のユーザーによるプログラムとスクリプトの実行を制限するように設計されています。 AppLocker の詳細とガイダンスについては、「 [applocker とは](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker)」をご覧ください。

AppLocker を使用してチームを有効化するプロセスでは、AppLocker ベースの空白のポリシーを作成する必要があります。 ポリシーは、グループポリシー管理ソフトウェアまたは AppLocker の Windows PowerShell コマンドレットを使用して作成されます (詳細については、「 [applocker のテクニカルリファレンス](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)」を参照してください)。 AppLocker ポリシーは XML 形式で保存され、任意のテキストエディターまたは XML エディターで編集できます。

## <a name="teams-whitelisting-with-applocker"></a>AppLocker を使ったチームの空白の置き換え

AppLocker ルールは、ルールのコレクションに整理されます。 AppLocker の規則はターゲットアプリに適用され、AppLocker ポリシーを構成するコンポーネントです。  

チームのホワイトリストを作成するには、すべての Teams アプリファイルがデジタル署名されているため、 [publisher の条件ルール](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker)を使用することをお勧めします。
  
Teams のインストールディレクトリはユーザーが書き込み可能であるため、パスルールを使用することはお勧めしません。 また、ルールは Teams クライアントアプリが更新されるたびに更新される必要があるため、ハッシュ規則を使用することはお勧めしません。

Teams のデスクトップの実行可能ファイルにはデジタル署名が行われるため、発行元の条件では、デジタル署名と埋め込みバージョンの属性に基づいてアプリファイルが識別されます。 デジタル署名には、アプリファイル (発行元) を作成した会社に関する情報が含まれています。 バイナリリソースから取得されるバージョン情報には、ファイルが含まれている製品の名前と、アプリケーションファイルのバージョン番号が含まれています。

### <a name="example-of-publisher-condition-rules"></a>Publisher の条件ルールの例

Teams クライアントアプリ (すべてのファイル、すべてのバージョン) については、次を実行可能ファイルの規則 & DLL の規則に追加します。

```
Publisher: O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US
Product name: MICROSOFT TEAMS
Product name: MICROSOFT TEAMS UPDATE
```

## <a name="related-topics"></a>関連項目
[AppLocker とは何ですか?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker)
 [AppLocker のテクニカルリファレンス](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)
