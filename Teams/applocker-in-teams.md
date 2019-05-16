---
title: マイクロソフトのチームで、AppLocker アプリケーション制御ポリシー
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: rafarhi
search.appverid: MET150
description: チーム デスクトップ クライアント アプリケーションには、AppLocker アプリケーション制御ポリシーを有効にする方法を説明します。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 04379cad0ab224915a02475b010f908d486284cc
ms.sourcegitcommit: 85b135cf622c9e9eb1857ef953bc618dc2cdb51e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "34063212"
---
# <a name="applocker-application-control-policies-in-microsoft-teams"></a>マイクロソフトのチームで、AppLocker アプリケーション制御ポリシー

この資料では、AppLocker アプリケーション制御ポリシーを使用してチームのデスクトップ クライアント アプリケーションを有効にする方法について説明します。 AppLocker を使用して、管理者以外のユーザーによってプログラムとスクリプトの実行を制限するのには設計されています。 詳細および AppLocker のガイダンスについてを参照してください[AppLocker は何ですか?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker)です。

AppLocker でチームを有効にするプロセスには、whitelisting の AppLocker ベースのポリシーの作成が必要です。 AppLocker の Windows PowerShell コマンドレットの使用および/または、グループ ポリシーの管理ソフトウェアとポリシーが作成されます (詳細については、 [AppLocker のテクニカル リファレンス](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)を参照してください)。 AppLocker のポリシーは、XML 形式で保存され、テキスト エディターまたは XML エディターで編集することができます。

## <a name="teams-whitelisting-with-applocker"></a>AppLocker でチームの whitelisting

AppLocker の規則は、規則のコレクションに編成されます。 AppLocker の規則の適用対象となるアプリケーションに、AppLocker のポリシーを構成するコンポーネントです。  

ホワイト リストのチームにチームのすべてのアプリケーション ファイルがデジタル署名されているために、[発行元の条件の規則](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker)を使用することをお勧めします。
  
チームのインストール ディレクトリは、ユーザーが書き込み可能なために、パスの規則の使用を推奨しません。 推奨しませんハッシュの規則の使用規則は、チームのクライアント アプリケーションが更新されるたびに更新する必要があるため。

チーム デスクトップの実行可能ファイルにデジタル署名であるために、発行元の条件はデジタル署名や埋め込みのバージョンの属性に基づいて、アプリケーションのファイルを識別します。 デジタル署名には、アプリケーション ファイル (発行元) を作成した会社に関する情報が含まれています。 バージョンについてには、バイナリのリソースから取得されるには、ファイルが含まれる製品およびアプリケーション ファイルのバージョン番号の名前が含まれています。

### <a name="example-of-publisher-condition-rules"></a>発行元の条件のルールの例

チーム クライアント アプリケーション (すべてのファイル、すべてのバージョン)。

```
Publisher: O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US
Product name: MICROSOFT TEAMS
```

## <a name="related-topics"></a>関連トピック
[AppLocker は何ですか?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker)
 [AppLocker のテクニカル リファレンス](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)