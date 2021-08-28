---
title: Skype for Business Server コンポーネントのセットアップまたは削除
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainBootstrap
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: f8813f25-eafa-4006-a186-94e4ebcc5ac7
description: '2015 コンポーネントをインストールおよびアクティブ化、または非アクティブ化またはアンインストールするにはSkype for Business Server手順 2: セットアップまたは削除を使用して、サーバー コンポーネントSkypeします。 インストールまたは変更するコンピューターのローカル管理者としてログインし、現在のドメイン内の Active Directory ドメイン サービスのユーザーとグループを読み取る必要があります。 開始するには、[実行] をクリックします。 これにより、中央管理ストアベースのトポロジ定義が読み取られます。 中央管理ストアに定義されている役割に従って、必要なソフトウェア コンポーネントがインストールされて構成されます。 インストールが完了したら、概要を確認し、[完了] をクリックします。'
ms.openlocfilehash: 267a4be0f2077d9cfd1d422d87c5916ab7486ac9
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58628929"
---
# <a name="setup-or-remove-skype-for-business-server-components"></a>Skype for Business Server コンポーネントのセットアップまたは削除
 
2015 コンポーネントのインストールとアクティブ化、または非アクティブ化またはアンインストールをSkype for Business Serverするには、「手順 **2:** セットアップまたは削除」サーバー コンポーネントを使用Skypeします。 インストールまたは変更するコンピューターのローカル管理者としてログインし、現在のドメイン内の Active Directory ドメイン サービスのユーザーとグループを読み取る必要があります。 開始するには、**[実行]** をクリックします。 これにより、中央管理ストアベースのトポロジ定義が読み取られます。 中央管理ストアに定義されている役割に従って、必要なソフトウェア コンポーネントがインストールされて構成されます。 インストールが完了したら、概要を確認し、[**完了**] をクリックします。
  
> [!TIP]
> 展開ウィザードによって作成されたログ ファイルを確認する必要がある場合は、展開ウィザードが実行されたコンピューターで、手順を実行した Active Directory ユーザーの Users ディレクトリにあります。 たとえば、ユーザーがドメイン Contoso.net のドメイン管理者としてログインした場合、ログ ファイルは > C:\Users\Administrator.Contoso\AppData\Local\Temp にあります。 
  
> [!NOTE]
> このコンピューターに Skype for Business Server 2015 コンポーネントを以前にインストールした場合、展開ウィザードはこれを認識し、手順 2 のボタンは [もう一度実行] と **表示されます**。 これにより、サーバーを適切に構成または変更するために、必要に応じて何度でも手順を実行できます。 
  

