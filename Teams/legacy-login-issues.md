---
title: Teamsのレガシ システムでのメッセージと呼び出しの受信に関する問題
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
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
description: レガシ システムでのメッセージと呼び出しの受信に関連する問題のトラブルシューティング
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 8ce2fa8d6a02a9da780681aba12dfe29b649f438
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62413480"
---
# <a name="issues-receiving-messages-and-calls-on-legacy-systems"></a>レガシ システムでのメッセージと呼び出しの受信に関する問題

ユーザーが以前のバージョンのTeamsを使用しているか、他のアプリケーションでログインしている場合、メッセージや呼び出しの受信に問題が発生する可能性があります。

## <a name="legacy-adu-setups"></a>従来の ADU セットアップ

 ドメインに参加しているコンピューターにユーザーがサインインしている場合に、**Teams のサインイン画面にユーザー名を事前入力させたくない場合** は、管理者は次の Windows レジストリを設定してユーザー名 (UPN) の事前入力を無効にできます。

  Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams<br/>
  SkipUpnPrefill(REG_DWORD)<br/>
  0x00000001 (1)

> [!NOTE]
> 「.local」 または 「.corp」 で終わるユーザー名については、ユーザー名の事前入力のスキップは既定でオンになっているため、レジストリ キーを設定してオフにする必要はありません。

詳細については、「[先進認証を使用してMicrosoft Teamsにサインイン](sign-in-teams.md)する」を参照してください。

## <a name="skype-token-revocation"></a>Skype トークン失効

パスワードを変更/リセットすると、古いクライアントは最大 1 時間メッセージと通話を受信しません。 この問題を解決するには、アプリを再起動するか、新しいクライアントに移動します。


## <a name="related-topics"></a>関連項目

[Teams のトラブルシューティング](/MicrosoftTeams/troubleshoot/teams)