---
title: レガシ システムでのメッセージと呼び出しの受信に関するTeams
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
description: レガシ システムでのメッセージと呼び出しの受信に関する問題のトラブルシューティング
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
<a name="issues-receiving-messages-and-calls-on-legacy-systems"></a>レガシ システムでのメッセージと呼び出しの受信に関する問題
==============================================================

以前のバージョンのアプリケーションを使用している場合、または他のアプリケーションでログインしている場合、Teamsまたは呼び出しの受信に問題がある可能性があります。

## <a name="legacy-adu-setups"></a>従来の ADU セットアップ

 ドメインに参加しているコンピューターにユーザーがサインインしている場合に、**Teams のサインイン画面にユーザー名を事前入力させたくない場合** は、管理者は次の Windows レジストリを設定してユーザー名 (UPN) の事前入力を無効にできます。

  Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams<br/>
  SkipUpnPrefill(REG_DWORD)<br/>
  0x00000001 (1)

> [!NOTE]
> 「.local」 または 「.corp」 で終わるユーザー名については、ユーザー名の事前入力のスキップは既定でオンになっているため、レジストリ キーを設定してオフにする必要はありません。

詳細については[、「最新の認証をMicrosoft Teamsサインインする」](sign-in-teams.md)を参照してください。

## <a name="skype-token-revocation"></a>Skypeトークンの失効

パスワードを変更/リセットすると、古いクライアントは最大 1 時間メッセージと呼び出しを受信しません。 この問題を解決するには、アプリを再起動するか、新しいクライアントに移動します。


## <a name="related-topics"></a>関連トピック

[Teams のトラブルシューティング](/MicrosoftTeams/troubleshoot/teams)