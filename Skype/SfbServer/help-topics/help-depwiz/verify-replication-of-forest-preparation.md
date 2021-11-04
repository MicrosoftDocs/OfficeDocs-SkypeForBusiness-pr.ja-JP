---
title: フォレスト準備のレプリケーションの確認
ms.reviewer: ''
ms.author: v-mahoffman
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
ms.localizationpriority: medium
ms.assetid: 94e87632-7c28-43df-9238-f5a47c1c43c0
description: フォレストの準備中にグローバル カタログのレプリケーションとオブジェクトの作成が成功したことを確認するには、次の手順を実行します。
ms.openlocfilehash: 845a53bc466dc586b63eaf8427c3e0ba23800886
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60744773"
---
# <a name="verify-replication-of-forest-preparation"></a>フォレスト準備のレプリケーションの確認
 
フォレストの準備中にグローバル カタログのレプリケーションとオブジェクトの作成が成功したことを確認するには、次の手順を実行します。
  
1. ドメイン コントローラー (できれば、他のドメイン コントローラーからのリモート サイト) で、フォレスト準備が実行されたフォレストで **、Active Directory Users** and Computers を開きます。
    
2. **[Active Directory ユーザーとコンピューター]** で、フォレストまたは子ドメインのドメイン名を展開します。
    
3. 左側の **ウィンドウで [Users]** コンテナーをクリックし、右側のウィンドウでユニバーサル グループ CsAdministrator を探します。 CsAdministrator (Cs で始まる 8 つの新しいユニバーサル グループの中で) が存在する場合、フォレスト準備のレプリケーションが成功しました。
    
4. グループが表示されていない場合、レプリケーションを強制的に実行するか、15 分待ってから右側のウィンドウを更新することができます。グループが表示されている場合、レプリケーションは完了しています。
    
> [!TIP]
> Skype for Business Server 展開ウィザードによって作成されたログ ファイルを確認する場合は、展開ウィザードが実行されたコンピューターで、手順を実行した Active Directory ドメイン サービス ユーザーの Users ディレクトリにあります。 たとえば、ユーザーがドメイン Contoso.net でドメイン管理者としてログインした場合、ログ ファイルは C:\Users\Administrator.Contoso\AppData\Local\Temp にあります。 
  

