---
title: "Who に対するアクセス許可を構成する"
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 12/07/2017
ms.topic: article
ms.service: msteams
description: "Microsoft Teams での Cloud Voice の機能の展開についての実践的なガイダンス"
Set_Free_Tag: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 629a732b178f6702f5ba308c6d0effe069019091
ms.sourcegitcommit: 85105cb4e42ae8eb6e7e76eaf6d4dd5b9568cf41
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2018
---
<a name="configure-permissions-for-who"></a>Who に対するアクセス許可を構成する
=============================

ユーザーは Microsoft Teams とともに Who アプリを使用して、質問をしたり、組織内のユーザーを、その仕事の内容や誰と働いているかに基づいて、検索したりすることができます。

ユーザーが Who を最大限有効活用できるようにするには、Microsoft Graph で次のメンバー アクセス許可をオンにする必要があります。

- Calendars.Read

- Calendars.Read.Shared

- Mail.Read

- MailboxSettings.ReadWrite

- People.Read

- People.Read.All

- Sites.Read.All

- User.Read.All

Microsoft Graph のアクセス許可の範囲の管理方法の詳細については、「[アクセス許可スコープ](https://msdn.microsoft.com/Library/Azure/Ad/Graph/howto/azure-ad-graph-api-permission-scopes)」をご覧ください。
 
Microsoft Graph のアクセス許可の詳細については、「[Microsoft Graph のアクセス許可のリファレンス](https://developer.microsoft.com/graph/docs/concepts/permissions_reference)」をご覧ください。