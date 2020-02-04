---
title: フォレスト準備のレプリケーションの確認
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployMainVerifyForestPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 94e87632-7c28-43df-9238-f5a47c1c43c0
ROBOTS: NOINDEX, NOFOLLOW
description: グローバルカタログの複製と、フォレストの準備中のオブジェクトの作成が正常に完了したことを確認するには、次の操作を行います。
ms.openlocfilehash: a89e5b1d8dff3f37def101b1cf2cccfad9d1bd5c
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41691752"
---
# <a name="verify-replication-of-forest-preparation"></a>フォレスト準備のレプリケーションの確認
 
グローバルカタログの複製と、フォレストの準備中のオブジェクトの作成が正常に完了したことを確認するには、次の操作を行います。
  
1. フォレストの準備を実行したフォレスト内のドメイン コントローラー (他のドメイン コントローラーからリモート サイトにあるドメイン コントローラーを推奨) で、[**Active Directory ユーザーとコンピューター**] を開きます。
    
2. [**Active Directory ユーザーとコンピューター**] で、フォレストまたは子ドメインのドメイン名を展開します。
    
3. 左側のウィンドウで [**ユーザー** ] コンテナーをクリックし、右側のウィンドウでユニバーサルグループ csadministrator を探します。 CsAdministrator (Cs で始まる8つの新しいユニバーサルグループの一部) が表示されている場合は、フォレストの準備の複製が正常に完了しています。
    
4. グループがまだ存在していない場合は、複製を強制するか、15分間待ってから右側のウィンドウを更新することができます。 グループが表示されている場合、レプリケーションは完了しています。
    
> [!TIP]
> Skype for Business Server 展開ウィザードによって作成されたログファイルを確認する場合は、その手順を実行した Active Directory ドメインサービスユーザーの Users ディレクトリで展開ウィザードが実行されているコンピューターで見つけることができます。 たとえば、ユーザーがドメイン Contoso.net のドメイン管理者としてログインしている場合、ログファイルは C:\Users\Administrator.Contoso\AppData\Local\Temp にあります。 
  

