---
title: Active Directory の準備
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainADPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: a8c96311-9e1c-4d39-9870-681fd4e272ff
ROBOTS: NOINDEX, NOFOLLOW
description: サーバーとユーザーをホストSkype for Business Server Active Directory ドメイン サービス スキーマ、フォレスト、およびドメインを準備する必要があります。 このSkype for Business Serverウィザードでは、Active Directory の準備に必要な手順を、スキーマからフォレストの準備まで順に説明します。 Active Directory レプリケーションが成功したと確認したら、ユーザーまたはサーバーをホストする各ドメインを準備します。
ms.openlocfilehash: c8973d9f5e269a9ebea48c81c70e68d74759eb92
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60755330"
---
# <a name="prepare-active-directory"></a>Active Directory の準備

サーバーとユーザーをホストSkype for Business Server Active Directory ドメイン サービス スキーマ、フォレスト、およびドメインを準備する必要があります。 このSkype for Business Serverウィザードでは、Active Directory の準備に必要な手順を、スキーマからフォレストの準備まで順に説明します。 Active Directory レプリケーションが成功したと確認したら、ユーザーまたはサーバーをホストする各ドメインを準備します。

> [!IMPORTANT]
> スキーマの準備を成功させるには、Enterprise Admins グループおよび Schema Admins グループのメンバーとしてログインする必要があります。フォレストを準備するには、Enterprise Admins グループのメンバーとしてログインするか、フォレスト ルートの管理者としてログインする必要があります。ドメインを準備するには、Domain Admins グループのメンバーとしてログインする必要があります。

サポートされる Active Directory のトポロジの詳細については、「サポート」のドキュメントの「[Active Directory Support](/previous-versions/office/lync-server-2013/lync-server-2013-active-directory-support)」を参照してください。Active Directory の準備の詳細については、「展開」のドキュメントの「[Overview of Active Directory Domain Services Preparation](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-active-directory-domain-services-preparation)」を参照してください。