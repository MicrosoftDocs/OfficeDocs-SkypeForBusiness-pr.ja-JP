---
title: フォレスト準備のレプリケーションの確認
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainVerifyForestPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 94e87632-7c28-43df-9238-f5a47c1c43c0
description: フォレストの準備中にグローバル カタログのレプリケーションとオブジェクトの作成が正常に行されたことを確認するには、次の手順を実行します。
ms.openlocfilehash: 010cf3fbadf8e07b4ccb80c33c34057024dde896
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800557"
---
# <a name="verify-replication-of-forest-preparation"></a>フォレスト準備のレプリケーションの確認
 
フォレストの準備中にグローバル カタログのレプリケーションとオブジェクトの作成が正常に行されたことを確認するには、次の手順を実行します。
  
1. ドメイン コントローラー (他のドメイン コントローラーからのリモート サイトが望ましい) で、フォレストの準備が実行されたフォレストで、Active Directory ユーザーとコンピューター **を開きます**。
    
2. **[Active Directory ユーザーとコンピューター]** で、フォレストまたは子ドメインのドメイン名を展開します。
    
3. 左側の **ウィンドウで Users** コンテナーをクリックし、右側のウィンドウでユニバーサル グループ CsAdministrator を探します。 CsAdministrator (Cs で始まる他の 8 つの新しいユニバーサル グループ間) が存在する場合、フォレストの準備のレプリケーションは成功しています。
    
4. グループが表示されていない場合、レプリケーションを強制的に実行するか、15 分待ってから右側のウィンドウを更新することができます。グループが表示されている場合、レプリケーションは完了しています。
    
> [!TIP]
> Skype for Business Server 展開ウィザードによって作成されたログ ファイルを確認する場合は、展開ウィザードが実行されたコンピューターの手順を実行した Active Directory ドメイン サービス ユーザーの Users ディレクトリでログ ファイルを見つける必要があります。 たとえば、ユーザーがドメイン Contoso.net でドメイン管理者としてログインした場合、ログ ファイルは C:\Users\Administrator.Contoso\AppData\Local\Temp にあります。 
  

