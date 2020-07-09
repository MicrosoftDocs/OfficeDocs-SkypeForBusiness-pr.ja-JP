---
title: Teams のレガシシステムでメッセージや通話を受信するときの問題
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
description: 従来のシステムでのメッセージの受信や通話に関する問題のトラブルシューティング
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: af7845b5fd6d50d63be6cd21749cbfedc7669fcf
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085153"
---
<a name="issues-receiving-messages-and-calls-on-legacy-systems"></a>従来のシステムでのメッセージと通話の受信に関する問題
==============================================================

以前のバージョンの Teams を使用しているか、他のアプリケーションでログインしている場合、ユーザーはメッセージや通話を受信するときに問題が発生する可能性があります。

## <a name="legacy-adu-setups"></a>従来の ADU のセットアップ

 ドメインに参加しているコンピューターにユーザーがサインインしている場合に、**Teams のサインイン画面にユーザー名を事前入力させたくない場合**は、管理者は次の Windows レジストリを設定してユーザー名 (UPN) の事前入力を無効にできます。

  Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams<br/>
  SkipUpnPrefill(REG_DWORD)<br/>
  0x00000001 (1)

> [!NOTE]
> 「.local」 または 「.corp」 で終わるユーザー名については、ユーザー名の事前入力のスキップは既定でオンになっているため、レジストリ キーを設定してオフにする必要はありません。

詳細については、「[先進認証を使用して Microsoft Teams にサインインする](sign-in-teams.md)」を参照してください。

## <a name="skype-token-revocation"></a>Skype トークンの取り消し

パスワードを変更/リセットすると、以前のクライアントでは、1時間以内にメッセージや通話を受けることができなくなります。 この問題を解決するには、アプリを再起動するか、新しいクライアントに移動します。


## <a name="related-topics"></a>関連項目

[チームのトラブルシューティング](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)