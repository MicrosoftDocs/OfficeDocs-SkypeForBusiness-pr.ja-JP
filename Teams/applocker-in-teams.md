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
# <a name="applocker-application-control-policies-in-microsoft-teams"></a><span data-ttu-id="a49af-103">AppLocker アプリケーション制御ポリシー (Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a49af-103">AppLocker application control policies in Microsoft Teams</span></span>

<span data-ttu-id="a49af-104">この記事では、AppLocker アプリケーション制御ポリシーをTeamsデスクトップ クライアント アプリを有効にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a49af-104">This article explains how to enable the Teams desktop client app with AppLocker application control policies.</span></span> <span data-ttu-id="a49af-105">AppLocker の使用は、管理者以外のユーザーによるプログラムとスクリプトの実行を制限するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="a49af-105">Use of AppLocker is designed to restrict program and script execution by non-administrative users.</span></span> <span data-ttu-id="a49af-106">AppLocker の詳細とガイダンスについては、「AppLocker とは [」を参照してください](/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker)。</span><span class="sxs-lookup"><span data-stu-id="a49af-106">For more information and guidance on AppLocker, see [What is AppLocker?](/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker).</span></span>

<span data-ttu-id="a49af-107">AppLocker を使用してTeamsするには、AppLocker ベースの許可リストポリシーを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a49af-107">The process for enabling Teams with AppLocker requires the creation of AppLocker-based allow listing policies.</span></span> <span data-ttu-id="a49af-108">ポリシーは、AppLocker のグループ ポリシー管理ソフトウェアや Windows PowerShell コマンドレットを使用して作成されます (詳細については[、AppLocker](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)のテクニカル リファレンスを参照してください)。</span><span class="sxs-lookup"><span data-stu-id="a49af-108">Policies are created with Group Policy management software and/or the use of Windows PowerShell cmdlets for AppLocker (see the [AppLocker technical reference](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference) for more information).</span></span> <span data-ttu-id="a49af-109">AppLocker ポリシーは XML 形式で保存され、任意のテキストエディターまたは XML エディターで編集できます。</span><span class="sxs-lookup"><span data-stu-id="a49af-109">The AppLocker policy is saved in XML format and can be edited with any text or XML editor.</span></span>

## <a name="teams-allow-list-with-applocker"></a><span data-ttu-id="a49af-110">appLocker Teams許可リストを作成する</span><span class="sxs-lookup"><span data-stu-id="a49af-110">Teams allow list with AppLocker</span></span>

<span data-ttu-id="a49af-111">AppLocker ルールは、ルールのコレクションに編成されます。</span><span class="sxs-lookup"><span data-stu-id="a49af-111">AppLocker rules are organized into collections of rules.</span></span> <span data-ttu-id="a49af-112">AppLocker ルールは対象のアプリに適用され、AppLocker ポリシーを構成するコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="a49af-112">AppLocker rules apply to the targeted app, and they are the components that make up the AppLocker policy.</span></span>  

<span data-ttu-id="a49af-113">アプリ ファイルTeams、すべてのアプリ ファイルがデジタル署名Teams[](/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker)条件ルールを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a49af-113">To allow Teams, we recommend that you use the [publisher condition rules](/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker) since all Teams app files are digitally signed.</span></span>
  
<span data-ttu-id="a49af-114">インストール ディレクトリはユーザーが書き込み可能なので、パスTeams使用はお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="a49af-114">We don't recommend the use of path rules because the Teams installation directory is user-writable.</span></span> <span data-ttu-id="a49af-115">また、クライアント アプリが更新されるごとにルールを更新する必要Teamsハッシュ 規則の使用はお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="a49af-115">We also don't recommend the use of hash rules because the rules would have to be updated each time the Teams client app is updated.</span></span>

<span data-ttu-id="a49af-116">デスクトップTeamsファイルがデジタル署名されている場合、発行元の条件はデジタル署名と埋め込みバージョン属性に基づいてアプリ ファイルを識別します。</span><span class="sxs-lookup"><span data-stu-id="a49af-116">Since Teams desktop executable files are digitally signed, the publisher condition identifies an app file based on its digital signature and embedded version attributes.</span></span> <span data-ttu-id="a49af-117">デジタル署名には、アプリ ファイル (発行元) を作成した会社に関する情報が含まれている。</span><span class="sxs-lookup"><span data-stu-id="a49af-117">The digital signature contains information about the company that created the app file (the publisher).</span></span> <span data-ttu-id="a49af-118">バイナリ リソースから取得されるバージョン情報には、ファイルが含まれる製品の名前とアプリケーション ファイルのバージョン番号が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a49af-118">The version information, which is obtained from the binary resource, includes the name of the product that the file is part of and the version number of the application file.</span></span>

### <a name="example-of-publisher-condition-rules"></a><span data-ttu-id="a49af-119">発行元の条件ルールの例</span><span class="sxs-lookup"><span data-stu-id="a49af-119">Example of publisher condition rules</span></span>

<span data-ttu-id="a49af-120">新しいTeams クライアント アプリ (すべてのファイル、すべてのバージョン) で、次のコードを DLL ルールの実行可能&追加します。</span><span class="sxs-lookup"><span data-stu-id="a49af-120">For the Teams client app (all files, all versions) add the following to the Executable Rules & DLL Rules:</span></span>

```console
Publisher: O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US
Product name: MICROSOFT TEAMS
Product name: MICROSOFT TEAMS UPDATE
```

## <a name="related-topics"></a><span data-ttu-id="a49af-121">関連トピック</span><span class="sxs-lookup"><span data-stu-id="a49af-121">Related topics</span></span>
<span data-ttu-id="a49af-122">[AppLocker とは](/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker) 
[AppLocker のテクニカル リファレンス](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)</span><span class="sxs-lookup"><span data-stu-id="a49af-122">[What is AppLocker?](/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker)
[AppLocker technical reference](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)</span></span>