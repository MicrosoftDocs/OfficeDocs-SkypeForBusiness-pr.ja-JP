---
title: Who に対するアクセス許可を構成する
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 12/07/2017
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Microsoft Teams での Cloud Voice の機能の展開についての実践的なガイダンス
Set_Free_Tag: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 20b556395c655d5052c328416d0f5ea64aee71ec
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2018
ms.locfileid: "25015838"
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