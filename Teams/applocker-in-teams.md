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
# <a name="applocker-application-control-policies-in-microsoft-teams"></a><span data-ttu-id="4bb24-103">Microsoft Teams の AppLocker アプリケーション制御ポリシー</span><span class="sxs-lookup"><span data-stu-id="4bb24-103">AppLocker application control policies in Microsoft Teams</span></span>

<span data-ttu-id="4bb24-104">この記事では、AppLocker アプリケーション制御ポリシーを使用して Teams デスクトップ クライアント アプリを有効にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4bb24-104">This article explains how to enable the Teams desktop client app with AppLocker application control policies.</span></span> <span data-ttu-id="4bb24-105">AppLocker の使用は、管理者以外のユーザーによるプログラムとスクリプトの実行を制限するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="4bb24-105">Use of AppLocker is designed to restrict program and script execution by non-administrative users.</span></span> <span data-ttu-id="4bb24-106">AppLocker の詳細とガイダンスについては [、「AppLocker とは何ですか?」を参照してください](/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker)。</span><span class="sxs-lookup"><span data-stu-id="4bb24-106">For more information and guidance on AppLocker, see [What is AppLocker?](/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker).</span></span>

<span data-ttu-id="4bb24-107">AppLocker で Teams を有効にするプロセスには、AppLocker ベースの許可リスト ポリシーの作成が必要です。</span><span class="sxs-lookup"><span data-stu-id="4bb24-107">The process for enabling Teams with AppLocker requires the creation of AppLocker-based allow listing policies.</span></span> <span data-ttu-id="4bb24-108">ポリシーは、グループ ポリシー管理ソフトウェア、および AppLocker の Windows PowerShell コマンドレットの使用 (詳細については [AppLocker](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference) のテクニカル リファレンスを参照) で作成されます。</span><span class="sxs-lookup"><span data-stu-id="4bb24-108">Policies are created with Group Policy management software and/or the use of Windows PowerShell cmdlets for AppLocker (see the [AppLocker technical reference](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference) for more information).</span></span> <span data-ttu-id="4bb24-109">AppLocker ポリシーは XML 形式で保存され、任意のテキストまたは XML エディターで編集できます。</span><span class="sxs-lookup"><span data-stu-id="4bb24-109">The AppLocker policy is saved in XML format and can be edited with any text or XML editor.</span></span>

## <a name="teams-allow-list-with-applocker"></a><span data-ttu-id="4bb24-110">AppLocker を使用した Teams の許可リスト</span><span class="sxs-lookup"><span data-stu-id="4bb24-110">Teams allow list with AppLocker</span></span>

<span data-ttu-id="4bb24-111">AppLocker ルールは、ルールのコレクションに編成されます。</span><span class="sxs-lookup"><span data-stu-id="4bb24-111">AppLocker rules are organized into collections of rules.</span></span> <span data-ttu-id="4bb24-112">AppLocker ルールは対象のアプリに適用され、これらは AppLocker ポリシーを構成するコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="4bb24-112">AppLocker rules apply to the targeted app, and they are the components that make up the AppLocker policy.</span></span>  

<span data-ttu-id="4bb24-113">Teams を許可するには、すべての Teams[](/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker)アプリ ファイルがデジタル署名された状態で発行元の条件ルールを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4bb24-113">To allow Teams, we recommend that you use the [publisher condition rules](/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker) since all Teams app files are digitally signed.</span></span>
  
<span data-ttu-id="4bb24-114">Teams のインストール ディレクトリはユーザーが書き込み可能なので、パス ルールの使用はお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="4bb24-114">We don't recommend the use of path rules because the Teams installation directory is user-writable.</span></span> <span data-ttu-id="4bb24-115">また、Teams クライアント アプリが更新されるごとにルールを更新する必要があるため、ハッシュ ルールの使用はお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="4bb24-115">We also don't recommend the use of hash rules because the rules would have to be updated each time the Teams client app is updated.</span></span>

<span data-ttu-id="4bb24-116">Teams デスクトップ実行可能ファイルはデジタル署名付きであるから、発行元の条件は、デジタル署名と埋め込みバージョン属性に基づいてアプリ ファイルを識別します。</span><span class="sxs-lookup"><span data-stu-id="4bb24-116">Since Teams desktop executable files are digitally signed, the publisher condition identifies an app file based on its digital signature and embedded version attributes.</span></span> <span data-ttu-id="4bb24-117">デジタル署名には、アプリ ファイル (発行元) を作成した会社に関する情報が含まれている。</span><span class="sxs-lookup"><span data-stu-id="4bb24-117">The digital signature contains information about the company that created the app file (the publisher).</span></span> <span data-ttu-id="4bb24-118">バイナリ リソースから取得されるバージョン情報には、ファイルが含まれる製品の名前とアプリケーション ファイルのバージョン番号が含まれます。</span><span class="sxs-lookup"><span data-stu-id="4bb24-118">The version information, which is obtained from the binary resource, includes the name of the product that the file is part of and the version number of the application file.</span></span>

### <a name="example-of-publisher-condition-rules"></a><span data-ttu-id="4bb24-119">発行元の条件ルールの例</span><span class="sxs-lookup"><span data-stu-id="4bb24-119">Example of publisher condition rules</span></span>

<span data-ttu-id="4bb24-120">Teams クライアント アプリ (すべてのファイル、すべてのバージョン) の場合は、DLL ルールの実行可能ルールに次&追加します。</span><span class="sxs-lookup"><span data-stu-id="4bb24-120">For the Teams client app (all files, all versions) add the following to the Executable Rules & DLL Rules:</span></span>

```console
Publisher: O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US
Product name: MICROSOFT TEAMS
Product name: MICROSOFT TEAMS UPDATE
```

## <a name="related-topics"></a><span data-ttu-id="4bb24-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="4bb24-121">Related topics</span></span>
<span data-ttu-id="4bb24-122">[AppLocker とは](/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker) 
[AppLocker のテクニカル リファレンス](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)</span><span class="sxs-lookup"><span data-stu-id="4bb24-122">[What is AppLocker?](/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker)
[AppLocker technical reference](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)</span></span>