---
title: Active Directory の準備
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainADPrep
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: a8c96311-9e1c-4d39-9870-681fd4e272ff
description: 2015 Skype for Business Serverのインストールを開始するには、サーバーとユーザーをホストする Active Directory ドメイン サービス スキーマ、フォレスト、およびドメインを準備する必要があります。 このSkype for Business Serverウィザードでは、Active Directory の準備に必要な手順を、スキーマからフォレストの準備まで順に説明します。 Active Directory レプリケーションが成功したと確認したら、ユーザーまたはサーバーをホストする各ドメインを準備します。
ms.openlocfilehash: 5882a9f016590b7e821f061d2a9db0e38ef2ab35
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60843080"
---
# <a name="prepare-active-directory"></a>Active Directory の準備

2015 Skype for Business Serverのインストールを開始するには、サーバーとユーザーをホストする Active Directory ドメイン サービス スキーマ、フォレスト、およびドメインを準備する必要があります。 このSkype for Business Serverウィザードでは、Active Directory の準備に必要な手順を、スキーマからフォレストの準備まで順に説明します。 Active Directory レプリケーションが成功したと確認したら、ユーザーまたはサーバーをホストする各ドメインを準備します。

> [!IMPORTANT]
> スキーマの準備を成功させるには、Enterprise Admins グループおよび Schema Admins グループのメンバーとしてログインする必要があります。フォレストを準備するには、Enterprise Admins グループのメンバーとしてログインするか、フォレスト ルートの管理者としてログインする必要があります。ドメインを準備するには、Domain Admins グループのメンバーとしてログインする必要があります。

サポートされる Active Directory のトポロジの詳細については、「サポート」のドキュメントの「[Active Directory Support](/previous-versions/office/lync-server-2013/lync-server-2013-active-directory-support)」を参照してください。Active Directory の準備の詳細については、「展開」のドキュメントの「[Overview of Active Directory Domain Services Preparation](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-active-directory-domain-services-preparation)」を参照してください。