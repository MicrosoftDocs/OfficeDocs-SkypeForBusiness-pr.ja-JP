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
# <a name="applocker-application-control-policies-in-microsoft-teams"></a><span data-ttu-id="70995-103">マイクロソフトのチームで、AppLocker アプリケーション制御ポリシー</span><span class="sxs-lookup"><span data-stu-id="70995-103">AppLocker application control policies in Microsoft Teams</span></span>

<span data-ttu-id="70995-104">この資料では、AppLocker アプリケーション制御ポリシーを使用してチームのデスクトップ クライアント アプリケーションを有効にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="70995-104">This article explains how to enable the Teams desktop client app with AppLocker application control policies.</span></span> <span data-ttu-id="70995-105">AppLocker を使用して、管理者以外のユーザーによってプログラムとスクリプトの実行を制限するのには設計されています。</span><span class="sxs-lookup"><span data-stu-id="70995-105">Use of AppLocker is designed to restrict program and script execution by non-administrative users.</span></span> <span data-ttu-id="70995-106">詳細および AppLocker のガイダンスについてを参照してください[AppLocker は何ですか?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker)です。</span><span class="sxs-lookup"><span data-stu-id="70995-106">For more information and guidance on AppLocker, see [What is AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker).</span></span>

<span data-ttu-id="70995-107">AppLocker でチームを有効にするプロセスには、whitelisting の AppLocker ベースのポリシーの作成が必要です。</span><span class="sxs-lookup"><span data-stu-id="70995-107">The process for enabling Teams with AppLocker requires the creation of AppLocker-based whitelisting policies.</span></span> <span data-ttu-id="70995-108">AppLocker の Windows PowerShell コマンドレットの使用および/または、グループ ポリシーの管理ソフトウェアとポリシーが作成されます (詳細については、 [AppLocker のテクニカル リファレンス](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="70995-108">Policies are created with Group Policy management software and/or the use of Windows PowerShell cmdlets for AppLocker (see the [AppLocker technical reference](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference) for more information).</span></span> <span data-ttu-id="70995-109">AppLocker のポリシーは、XML 形式で保存され、テキスト エディターまたは XML エディターで編集することができます。</span><span class="sxs-lookup"><span data-stu-id="70995-109">The AppLocker policy is saved in XML format and can be edited with any text or XML editor.</span></span>

## <a name="teams-whitelisting-with-applocker"></a><span data-ttu-id="70995-110">AppLocker でチームの whitelisting</span><span class="sxs-lookup"><span data-stu-id="70995-110">Teams whitelisting with AppLocker</span></span>

<span data-ttu-id="70995-111">AppLocker の規則は、規則のコレクションに編成されます。</span><span class="sxs-lookup"><span data-stu-id="70995-111">AppLocker rules are organized into collections of rules.</span></span> <span data-ttu-id="70995-112">AppLocker の規則の適用対象となるアプリケーションに、AppLocker のポリシーを構成するコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="70995-112">AppLocker rules apply to the targeted app, and they are the components that make up the AppLocker policy.</span></span>  

<span data-ttu-id="70995-113">ホワイト リストのチームにチームのすべてのアプリケーション ファイルがデジタル署名されているために、[発行元の条件の規則](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker)を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="70995-113">To whitelist Teams, we recommend that you use the [publisher condition rules](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker) since all Teams app files are digitally signed.</span></span>
  
<span data-ttu-id="70995-114">チームのインストール ディレクトリは、ユーザーが書き込み可能なために、パスの規則の使用を推奨しません。</span><span class="sxs-lookup"><span data-stu-id="70995-114">We don't recommend the use of path rules because the Teams installation directory is user-writable.</span></span> <span data-ttu-id="70995-115">推奨しませんハッシュの規則の使用規則は、チームのクライアント アプリケーションが更新されるたびに更新する必要があるため。</span><span class="sxs-lookup"><span data-stu-id="70995-115">We also don't recommend the use of hash rules because the rules would have to be updated each time the Teams client app is updated.</span></span>

<span data-ttu-id="70995-116">チーム デスクトップの実行可能ファイルにデジタル署名であるために、発行元の条件はデジタル署名や埋め込みのバージョンの属性に基づいて、アプリケーションのファイルを識別します。</span><span class="sxs-lookup"><span data-stu-id="70995-116">Since Teams desktop executable files are digitally signed, the publisher condition identifies an app file based on its digital signature and embedded version attributes.</span></span> <span data-ttu-id="70995-117">デジタル署名には、アプリケーション ファイル (発行元) を作成した会社に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="70995-117">The digital signature contains information about the company that created the app file (the publisher).</span></span> <span data-ttu-id="70995-118">バージョンについてには、バイナリのリソースから取得されるには、ファイルが含まれる製品およびアプリケーション ファイルのバージョン番号の名前が含まれています。</span><span class="sxs-lookup"><span data-stu-id="70995-118">The version information, which is obtained from the binary resource, includes the name of the product that the file is part of and the version number of the application file.</span></span>

### <a name="example-of-publisher-condition-rules"></a><span data-ttu-id="70995-119">発行元の条件のルールの例</span><span class="sxs-lookup"><span data-stu-id="70995-119">Example of publisher condition rules</span></span>

<span data-ttu-id="70995-120">チーム クライアント アプリケーション (すべてのファイル、すべてのバージョン)。</span><span class="sxs-lookup"><span data-stu-id="70995-120">For the Teams client app (all files, all versions):</span></span>

```
Publisher: O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US
Product name: MICROSOFT TEAMS
```

## <a name="related-topics"></a><span data-ttu-id="70995-121">関連トピック</span><span class="sxs-lookup"><span data-stu-id="70995-121">Related topics</span></span>
<span data-ttu-id="70995-122">[AppLocker は何ですか?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker)
 [AppLocker のテクニカル リファレンス](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)</span><span class="sxs-lookup"><span data-stu-id="70995-122">[What is AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker)
[AppLocker technical reference](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)</span></span>