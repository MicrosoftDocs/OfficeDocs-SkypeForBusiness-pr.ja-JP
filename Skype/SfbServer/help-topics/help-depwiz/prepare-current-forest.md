---
title: 現在のフォレストの準備
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainForestPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11f5e359-97eb-45f7-a730-9ddbbaa40b83
description: Active Directory ドメインサービスフォレストを準備するには、「スキーマの準備を実行する」のトピックで説明されているように、スキーマを正常に拡張し、スキーマがレプリケートされていることを確認する必要があります。
ms.openlocfilehash: d13660eb703a793c1fc59ed422bd0b317986a86b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823531"
---
# <a name="prepare-current-forest"></a>現在のフォレストの準備

Active Directory ドメインサービスフォレストを準備するには、「[スキーマの準備を実行](https://technet.microsoft.com/library/067726ae-fd3f-4133-a32f-26d2603ac674.aspx)する」のトピックで説明されているように、スキーマを正常に拡張し、スキーマがレプリケートされていることを確認する必要があります。

これらの前提条件を満たしたら、[**手順 3: 現在のフォレストの準備**] を開始できます。フォレストを準備するには、フォレスト ルートのコンピューターに、フォレスト ルートの Domain Admins のメンバーとして、または準備しているフォレストの Enterprise Admins のメンバーとしてログオンします。

1. [**手順 3: 現在のフォレストの準備**] で、展開ウィザードから [**実行**] をクリックします。

2. [**フォレストの準備**] ページから、[**次へ**] をクリックします。

    > [!NOTE]
    > フォレストの準備 Skype for Business Server 2015 のユニバーサルグループを配置する場所を選ぶことができます。 組織の要件と一致する配置先を選択してください。

3. [**コマンドを実行しています**] ページで [**タスク状態: 完了**] を見つけて、[**ログの表示**] をクリックします。エラーがないことを確認します。警告を確認して、それらの警告が予期されるものであり、インフラストラクチャにとって通常のものであるかどうかを確認します。

4. ログの [**アクション**] 列で、[**フォレスト**の準備] を展開して、各タスクの最後の** \<成功\> **の実行結果を確認し、フォレストの準備が正常に完了したことを確認します。次に、[**完了**] をクリックします。

5. Active Directory ドメインサービスのレプリケーションが完了するまで待ちます。または、ドメインの準備を実行する前に、フォレストルートドメインコントローラーの [ **Active Directory サイトとサービス**] スナップインに記載されているすべてのドメインコントローラーに対して強制的にレプリケーションを実行します。 すべての Active Directory サイトのドメインコントローラー間で強制的にレプリケーションを実行して、サイト内での複製が分単位で行われるようにします。

    > [!TIP]
    > Skype for Business Server 展開ウィザードによって作成されたログファイルを確認する必要がある場合は、展開ウィザードが実行されているコンピューターで、手順を実行した Active Directory ドメインサービスユーザーの Users ディレクトリで見つけることができます。 たとえば、ユーザーがドメイン Contoso.net のドメイン管理者としてログインしている場合、ログファイルは C:\Users\Administrator.Contoso\AppData\Local\Temp にあります。


