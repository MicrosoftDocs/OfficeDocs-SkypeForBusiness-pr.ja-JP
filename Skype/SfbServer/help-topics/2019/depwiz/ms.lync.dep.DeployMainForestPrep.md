---
title: 現在のフォレストの準備
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainForestPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11f5e359-97eb-45f7-a730-9ddbbaa40b83
description: Active Directory ドメイン サービス フォレストを準備するには、正常にスキーマの準備の実行中のトピックで説明したように、スキーマを拡張して、スキーマがレプリケートされたことを確認する必要があります。
ms.openlocfilehash: f993236fc13fc2274acaa8bb4c6b0ae1105afccb
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/21/2018
ms.locfileid: "19987488"
---
# <a name="prepare-current-forest"></a>現在のフォレストの準備
 
Active Directory ドメイン サービス フォレストを準備するには、正常に[スキーマの準備を実行して](http://technet.microsoft.com/library/067726ae-fd3f-4133-a32f-26d2603ac674.aspx)、トピックで説明したように、スキーマを拡張して、スキーマがレプリケートされたことを確認する必要があります。
  
これらの前提条件を満たしたら、[**手順 3: 現在のフォレストの準備**] を開始できます。フォレストを準備するには、フォレスト ルートのコンピューターに、フォレスト ルートの Domain Admins のメンバーとして、または準備しているフォレストの Enterprise Admins のメンバーとしてログオンします。
  
1. [**手順 3: 現在のフォレストの準備**] で、展開ウィザードから [**実行**] をクリックします。
    
2. [**フォレストの準備**] ページから、[**次へ**] をクリックします。
    
    > [!NOTE]
    > フォレストの準備では、Skype のビジネス サーバー 2015 のユニバーサル グループを配置する場所を選択できます。 組織の要件と一致する配置先を選択してください。 
  
3. [**コマンドを実行しています**] ページで [**タスク状態: 完了**] を見つけて、[**ログの表示**] をクリックします。エラーがないことを確認します。警告を確認して、それらの警告が予期されるものであり、インフラストラクチャにとって通常のものであるかどうかを確認します。
    
4. ログの [**アクション**] 列の下には、**フォレストの準備**を展開、検索、**\<成功\>** フォレストの準備が正常に完了したことを確認し、ログを閉じるし、 **[完了] をクリックし、各タスクの最後に実行の結果**.
    
5. 完了するには Active Directory ドメイン サービスのレプリケーションを待つか、ドメインの準備を実行する前に、 **Active Directory サイトとサービス**スナップインで、フォレスト ルート ドメイン コント ローラーに表示されているすべてのドメイン コント ローラーへのレプリケーションを強制的に。 分以内にサイト内でのレプリケーションが発生するすべての Active Directory サイト内のドメイン コント ローラー間のレプリケーションを強制します。
    
    > [!TIP]
    > ビジネス サーバーの展開ウィザードは、Skype によって作成されるログ ファイルを確認する必要がある場合、は、展開ウィザードが実行しているコンピューターの手順を実行した Active Directory ドメイン サービスのユーザーのユーザー ディレクトリ内にそれらを検索できます。 たとえば、ユーザー Contoso.net のドメインのドメイン管理者としてログインしている場合、ログ ・ ファイル内にある: C:\Users\Administrator.Contoso\AppData\Local\Temp 
  

