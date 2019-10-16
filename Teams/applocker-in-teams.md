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
ms.openlocfilehash: eb12012c0775d98c7d1b08b61c6c0deba83a4d5f
ms.sourcegitcommit: 5695ce88d4a6a8fb9594df8dd1c207e45be067be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "37516775"
---
# <a name="applocker-application-control-policies-in-microsoft-teams"></a><span data-ttu-id="e2f0f-103">Microsoft Teams の AppLocker アプリケーション制御ポリシー</span><span class="sxs-lookup"><span data-stu-id="e2f0f-103">AppLocker application control policies in Microsoft Teams</span></span>

<span data-ttu-id="e2f0f-104">この記事では、AppLocker アプリケーション制御ポリシーを使って Teams デスクトップクライアントアプリを有効にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e2f0f-104">This article explains how to enable the Teams desktop client app with AppLocker application control policies.</span></span> <span data-ttu-id="e2f0f-105">AppLocker の使用は、管理者以外のユーザーによるプログラムとスクリプトの実行を制限するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="e2f0f-105">Use of AppLocker is designed to restrict program and script execution by non-administrative users.</span></span> <span data-ttu-id="e2f0f-106">AppLocker の詳細とガイダンスについては、「 [applocker とは](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e2f0f-106">For more information and guidance on AppLocker, see [What is AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker).</span></span>

<span data-ttu-id="e2f0f-107">AppLocker を使用してチームを有効化するプロセスでは、AppLocker ベースの空白のポリシーを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2f0f-107">The process for enabling Teams with AppLocker requires the creation of AppLocker-based whitelisting policies.</span></span> <span data-ttu-id="e2f0f-108">ポリシーは、グループポリシー管理ソフトウェアまたは AppLocker の Windows PowerShell コマンドレットを使用して作成されます (詳細については、「 [applocker のテクニカルリファレンス](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="e2f0f-108">Policies are created with Group Policy management software and/or the use of Windows PowerShell cmdlets for AppLocker (see the [AppLocker technical reference](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference) for more information).</span></span> <span data-ttu-id="e2f0f-109">AppLocker ポリシーは XML 形式で保存され、任意のテキストエディターまたは XML エディターで編集できます。</span><span class="sxs-lookup"><span data-stu-id="e2f0f-109">The AppLocker policy is saved in XML format and can be edited with any text or XML editor.</span></span>

## <a name="teams-whitelisting-with-applocker"></a><span data-ttu-id="e2f0f-110">AppLocker を使ったチームの空白の置き換え</span><span class="sxs-lookup"><span data-stu-id="e2f0f-110">Teams whitelisting with AppLocker</span></span>

<span data-ttu-id="e2f0f-111">AppLocker ルールは、ルールのコレクションに整理されます。</span><span class="sxs-lookup"><span data-stu-id="e2f0f-111">AppLocker rules are organized into collections of rules.</span></span> <span data-ttu-id="e2f0f-112">AppLocker の規則はターゲットアプリに適用され、AppLocker ポリシーを構成するコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="e2f0f-112">AppLocker rules apply to the targeted app, and they are the components that make up the AppLocker policy.</span></span>  

<span data-ttu-id="e2f0f-113">チームのホワイトリストを作成するには、すべての Teams アプリファイルがデジタル署名されているため、 [publisher の条件ルール](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker)を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e2f0f-113">To whitelist Teams, we recommend that you use the [publisher condition rules](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker) since all Teams app files are digitally signed.</span></span>
  
<span data-ttu-id="e2f0f-114">Teams のインストールディレクトリはユーザーが書き込み可能であるため、パスルールを使用することはお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="e2f0f-114">We don't recommend the use of path rules because the Teams installation directory is user-writable.</span></span> <span data-ttu-id="e2f0f-115">また、ルールは Teams クライアントアプリが更新されるたびに更新される必要があるため、ハッシュ規則を使用することはお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="e2f0f-115">We also don't recommend the use of hash rules because the rules would have to be updated each time the Teams client app is updated.</span></span>

<span data-ttu-id="e2f0f-116">Teams のデスクトップの実行可能ファイルにはデジタル署名が行われるため、発行元の条件では、デジタル署名と埋め込みバージョンの属性に基づいてアプリファイルが識別されます。</span><span class="sxs-lookup"><span data-stu-id="e2f0f-116">Since Teams desktop executable files are digitally signed, the publisher condition identifies an app file based on its digital signature and embedded version attributes.</span></span> <span data-ttu-id="e2f0f-117">デジタル署名には、アプリファイル (発行元) を作成した会社に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e2f0f-117">The digital signature contains information about the company that created the app file (the publisher).</span></span> <span data-ttu-id="e2f0f-118">バイナリリソースから取得されるバージョン情報には、ファイルが含まれている製品の名前と、アプリケーションファイルのバージョン番号が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e2f0f-118">The version information, which is obtained from the binary resource, includes the name of the product that the file is part of and the version number of the application file.</span></span>

### <a name="example-of-publisher-condition-rules"></a><span data-ttu-id="e2f0f-119">Publisher の条件ルールの例</span><span class="sxs-lookup"><span data-stu-id="e2f0f-119">Example of publisher condition rules</span></span>

<span data-ttu-id="e2f0f-120">Teams クライアントアプリ (すべてのファイル、すべてのバージョン) の場合:</span><span class="sxs-lookup"><span data-stu-id="e2f0f-120">For the Teams client app (all files, all versions):</span></span>

```
Publisher: O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US
Product name: MICROSOFT TEAMS
```

## <a name="related-topics"></a><span data-ttu-id="e2f0f-121">関連トピック</span><span class="sxs-lookup"><span data-stu-id="e2f0f-121">Related topics</span></span>
<span data-ttu-id="e2f0f-122">[AppLocker とは何ですか?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker)
 [AppLocker のテクニカルリファレンス](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)</span><span class="sxs-lookup"><span data-stu-id="e2f0f-122">[What is AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker)
[AppLocker technical reference](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)</span></span>