---
title: Teams で従来のシステムでメッセージと通話を受信する問題
ms.reviewer: ''
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 05/29/2020
ms.topic: troubleshooting
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
description: 従来のシステムでのメッセージと通話の受信に関する問題のトラブルシューティング
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 1c209d1acc83e63792722b00b63be5a6b9f3721a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120608"
---
<a name="issues-receiving-messages-and-calls-on-legacy-systems"></a><span data-ttu-id="d82fe-103">従来のシステムでのメッセージと通話の受信に関する問題</span><span class="sxs-lookup"><span data-stu-id="d82fe-103">Issues receiving messages and calls on legacy systems</span></span>
==============================================================

<span data-ttu-id="d82fe-104">以前のバージョンの Teams を使用している場合、または他のアプリケーションでログインしている場合、ユーザーはメッセージまたは通話を受信する問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d82fe-104">Users might have issues receiving messages or calls if they are using older versions of Teams or have logged in with other applications.</span></span>

## <a name="legacy-adu-setups"></a><span data-ttu-id="d82fe-105">従来の ADU セットアップ</span><span class="sxs-lookup"><span data-stu-id="d82fe-105">Legacy ADU setups</span></span>

 <span data-ttu-id="d82fe-106">ドメインに参加しているコンピューターにユーザーがサインインしている場合に、**Teams のサインイン画面にユーザー名を事前入力させたくない場合** は、管理者は次の Windows レジストリを設定してユーザー名 (UPN) の事前入力を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="d82fe-106">If users are signed in to a domain-joined computer and you **don't want their user name pre-populated on the Teams sign-in screen**, admins can set the following Windows registry to turn off pre-population of the user name (UPN):</span></span>

  <span data-ttu-id="d82fe-107">Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams</span><span class="sxs-lookup"><span data-stu-id="d82fe-107">Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams</span></span><br/>
  <span data-ttu-id="d82fe-108">SkipUpnPrefill(REG_DWORD)</span><span class="sxs-lookup"><span data-stu-id="d82fe-108">SkipUpnPrefill(REG_DWORD)</span></span><br/>
  <span data-ttu-id="d82fe-109">0x00000001 (1)</span><span class="sxs-lookup"><span data-stu-id="d82fe-109">0x00000001 (1)</span></span>

> [!NOTE]
> <span data-ttu-id="d82fe-110">「.local」 または 「.corp」 で終わるユーザー名については、ユーザー名の事前入力のスキップは既定でオンになっているため、レジストリ キーを設定してオフにする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d82fe-110">Skipping or ignoring user name pre-fill for user names that end in ".local" or ".corp" is on by default, so you don't need to set a registry key to turn these off.</span></span>

<span data-ttu-id="d82fe-111">詳細 [については、「最新の認証を使用して Microsoft Teams](sign-in-teams.md) にサインインする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d82fe-111">See [Sign in to Microsoft Teams using modern authentication](sign-in-teams.md) for more information.</span></span>

## <a name="skype-token-revocation"></a><span data-ttu-id="d82fe-112">Skype トークン失効</span><span class="sxs-lookup"><span data-stu-id="d82fe-112">Skype token revocation</span></span>

<span data-ttu-id="d82fe-113">パスワードを変更またはリセットすると、古いクライアントは最大 1 時間、メッセージと通話を受信しません。</span><span class="sxs-lookup"><span data-stu-id="d82fe-113">When changing/resetting a password, older clients will not receive messages and calls for up to an hour.</span></span> <span data-ttu-id="d82fe-114">この問題を解決するには、アプリを再起動するか、新しいクライアントに移動します。</span><span class="sxs-lookup"><span data-stu-id="d82fe-114">To resolve this issue, either restart the app or move to newer clients.</span></span>


## <a name="related-topics"></a><span data-ttu-id="d82fe-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="d82fe-115">Related topics</span></span>

[<span data-ttu-id="d82fe-116">Teams のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="d82fe-116">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)