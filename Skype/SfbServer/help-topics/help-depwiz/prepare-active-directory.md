---
title: Active Directory の準備
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainADPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a8c96311-9e1c-4d39-9870-681fd4e272ff
description: Skype for Business Server 2015 のインストールを開始するには、サーバーとユーザーをホストする Active Directory ドメインサービスのスキーマ、フォレスト、ドメインを準備する必要があります。 Skype for Business Server 展開ウィザードでは、最初にスキーマを作成してから、フォレストの準備に至るまで、Active Directory の準備に必要な手順を実行します。 Active Directory の複製が正常に完了したことを確認したら、ユーザーまたはサーバーをホストする各ドメインを準備します。
ms.openlocfilehash: c2343d0c74d2ae46c7c2b22eaaa893f023f68297
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812035"
---
# <a name="prepare-active-directory"></a>Active Directory の準備

Skype for Business Server 2015 のインストールを開始するには、サーバーとユーザーをホストする Active Directory ドメインサービスのスキーマ、フォレスト、ドメインを準備する必要があります。 Skype for Business Server 展開ウィザードでは、最初にスキーマを作成してから、フォレストの準備に至るまで、Active Directory の準備に必要な手順を実行します。 Active Directory の複製が正常に完了したことを確認したら、ユーザーまたはサーバーをホストする各ドメインを準備します。

> [!IMPORTANT]
> スキーマの準備を成功させるには、Enterprise Admins グループおよび Schema Admins グループのメンバーとしてログインする必要があります。フォレストを準備するには、Enterprise Admins グループのメンバーとしてログインするか、フォレスト ルートの管理者としてログインする必要があります。ドメインを準備するには、Domain Admins グループのメンバーとしてログインする必要があります。

サポートされる Active Directory のトポロジの詳細については、「サポート」のドキュメントの「[Active Directory Support](https://technet.microsoft.com/library/28ed9ac4-586d-4803-ad45-99c4fa793f54.aspx)」を参照してください。Active Directory の準備の詳細については、「展開」のドキュメントの「[Overview of Active Directory Domain Services Preparation](https://technet.microsoft.com/library/cdd2a652-6a0d-4728-9950-3fcaa7a80066.aspx)」を参照してください。


