---
title: Skype for Business Server コンポーネントのセットアップまたは削除
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainBootstrap
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: f8813f25-eafa-4006-a186-94e4ebcc5ac7
ROBOTS: NOINDEX, NOFOLLOW
description: 'コンポーネントのインストールとアクティブ化、または非アクティブ化Skype for Business Serverするには、「手順 2: セットアップまたは削除」を使用して、サーバー Skypeします。 インストールまたは変更するコンピューターのローカル管理者としてログインし、現在のドメイン内の Active Directory ドメイン サービスのユーザーとグループを読み取る必要があります。 開始するには、[実行] をクリックします。 これにより、中央管理ストアベースのトポロジ定義が読み取られます。 中央管理ストアに定義されている役割に従って、必要なソフトウェア コンポーネントがインストールされて構成されます。 インストールが完了したら、概要を確認し、[完了] をクリックします。'
ms.openlocfilehash: 6bea150f7117fe30e1785d2494c7348171bba615ec884946c8e935b2475e9e25
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54282190"
---
# <a name="setup-or-remove-skype-for-business-server-components"></a>Skype for Business Server コンポーネントのセットアップまたは削除
 
コンポーネントをインストールおよびアクティブ化、または非アクティブ化またはアンインストールSkype for Business Serverするには、「手順 **2:** セットアップまたは削除」を使用して、サーバー コンポーネントSkype削除します。 インストールまたは変更するコンピューターのローカル管理者としてログインし、現在のドメイン内の Active Directory ドメイン サービスのユーザーとグループを読み取る必要があります。 開始するには、**[実行]** をクリックします。 これにより、中央管理ストアベースのトポロジ定義が読み取られます。 中央管理ストアに定義されている役割に従って、必要なソフトウェア コンポーネントがインストールされて構成されます。 インストールが完了したら、概要を確認し、[**完了**] をクリックします。
  
> [!TIP]
> 展開ウィザードによって作成されたログ ファイルを確認する必要がある場合は、展開ウィザードが実行されたコンピューターで、手順を実行した Active Directory ユーザーの Users ディレクトリにあります。 たとえば、ユーザーがドメイン Contoso.net のドメイン管理者としてログインした場合、ログ ファイルは > C:\Users\Administrator.Contoso\AppData\Local\Temp にあります。 
  
> [!NOTE]
> このコンピューターに Skype for Business Serverコンポーネントをインストールした場合、展開ウィザードはこれを認識し、手順 2 のボタンは [もう一度実行]**と表示されます**。 これにより、サーバーを適切に構成または変更するために、必要に応じて何度でも手順を実行できます。 
  

