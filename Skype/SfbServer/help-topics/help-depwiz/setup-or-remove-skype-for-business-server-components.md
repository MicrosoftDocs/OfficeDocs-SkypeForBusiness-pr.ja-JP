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
localization_priority: Normal
ms.assetid: f8813f25-eafa-4006-a186-94e4ebcc5ac7
description: 'Skype for Business Server 2015 コンポーネントをインストールしてアクティブ化または非アクティブ化またはアンインストールするには、「手順 2: Skype Server コンポーネントをセットアップまたは削除する」を使用します。 インストールまたは変更するコンピューターにローカル管理者としてログインし、現在のドメイン内の Active Directory ドメイン サービスのユーザーとグループを読み取る必要があります。 開始するには、[実行] をクリックします。 これにより、中央管理ストアベースのトポロジ定義が読み取られます。 中央管理ストアに定義されている役割に従って、必要なソフトウェア コンポーネントがインストールされて構成されます。 インストールが完了したら、概要を確認し、[完了] をクリックします。'
ms.openlocfilehash: 05144357e7346428c6c23f6482abd91a58e3779f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49829627"
---
# <a name="setup-or-remove-skype-for-business-server-components"></a>Skype for Business Server コンポーネントのセットアップまたは削除
 
Skype for Business Server 2015 コンポーネントをインストールしてアクティブ化または非アクティブ化またはアンインストールするには、「手順 2: Skype Server コンポーネントをセットアップまたは削除する **」を使用します**。 インストールまたは変更するコンピューターにローカル管理者としてログインし、現在のドメイン内の Active Directory ドメイン サービスのユーザーとグループを読み取る必要があります。 開始するには、**[実行]** をクリックします。 これにより、中央管理ストアベースのトポロジ定義が読み取られます。 中央管理ストアに定義されている役割に従って、必要なソフトウェア コンポーネントがインストールされて構成されます。 インストールが完了したら、概要を確認し、[**完了**] をクリックします。
  
> [!TIP]
> 展開ウィザードで作成されたログ ファイルを確認する必要がある場合は、展開ウィザードが実行されたコンピューターの手順を実行した Active Directory ユーザーの Users ディレクトリでログ ファイルを見つける必要があります。 たとえば、ユーザーがドメイン Contoso.net でドメイン管理者としてログインした場合、ログ ファイルは > C:\Users\Administrator.Contoso\AppData\Local\Temp にあります。 
  
> [!NOTE]
> このコンピューターに Skype for Business Server 2015 コンポーネントを以前にインストールしている場合は、展開ウィザードによってこの認識が行い、手順 2 のボタンが [再び実行] として **表示されます**。 これにより、サーバーを適切に構成または変更するために、必要に応じて何度でも手順を実行できます。 
  

