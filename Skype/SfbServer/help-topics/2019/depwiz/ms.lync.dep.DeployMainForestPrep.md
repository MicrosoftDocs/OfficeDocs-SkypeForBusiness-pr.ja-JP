---
title: 現在のフォレストの準備
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainForestPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: 11f5e359-97eb-45f7-a730-9ddbbaa40b83
ROBOTS: NOINDEX, NOFOLLOW
description: Active Directory ドメイン サービス フォレストを準備するには、「スキーマの準備の実行」の説明に従ってスキーマを正常に拡張し、スキーマがレプリケートされたことを確認する必要があります。
ms.openlocfilehash: 90d591b79bd4cdc82e5878b3e9173d19a0f48452
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58609794"
---
# <a name="prepare-current-forest"></a>現在のフォレストの準備

Active Directory ドメイン サービス フォレストを準備するには、「スキーマの準備を実行する」の説明[](/previous-versions/office/lync-server-2013/lync-server-2013-preparing-the-active-directory-schema)に従ってスキーマを正常に拡張し、スキーマがレプリケートされたことを確認する必要があります。

これらの前提条件を満たしたら、[**手順 3: 現在のフォレストの準備**] を開始できます。フォレストを準備するには、フォレスト ルートのコンピューターに、フォレスト ルートの Domain Admins のメンバーとして、または準備しているフォレストの Enterprise Admins のメンバーとしてログオンします。

1. [**手順 3: 現在のフォレストの準備**] で、展開ウィザードから [**実行**] をクリックします。

2. **[フォレストの準備]** ページから、**[次へ]** をクリックします。

    > [!NOTE]
    > フォレストの準備を使用すると、ユニバーサル グループを配置する場所を選択Skype for Business Server。 組織の要件と一致する配置先を選択してください。

3. [**コマンドを実行しています**] ページで [**タスク状態: 完了**] を見つけて、[**ログの表示**] をクリックします。エラーがないことを確認します。警告を確認して、それらの警告が予期されるものであり、インフラストラクチャにとって通常のものであることを確認します。

4. ログの **[アクション**] 列で、[フォレスト準備] を展開し、各タスクの最後に実行結果を探して、フォレストの準備が正常に完了したと確認し、ログを閉じて、[完了] を **\<Success\>** クリックします。 

5. Active Directory ドメイン サービスのレプリケーションが完了するのを待つか、フォレスト ルート ドメイン コントローラーの Active Directory Sites **and Services** スナップインに記載されているすべてのドメイン コントローラーへのレプリケーションを強制的に実行してから、ドメインの準備を実行します。 サイト内でレプリケーションが数分以内に開始されるよう、すべての Active Directory サイト内のドメイン コントローラ間でレプリケーションを強制的に実行します。

    > [!TIP]
    > Skype for Business Server 展開ウィザードによって作成されたログ ファイルを確認する必要がある場合は、展開ウィザードが実行されたコンピューターで、手順を実行した Active Directory ドメイン サービス ユーザーの Users ディレクトリにあります。 たとえば、ユーザーがドメイン Contoso.net でドメイン管理者としてログインした場合、ログ ファイルは C:\Users\Administrator.Contoso\AppData\Local\Temp にあります。