---
title: 現在のドメインの準備
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
- ms.lync.dep.DeployMainDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bfcb37ca-34eb-4d0d-9694-6edd2e7fe0f3
description: 'Skype for Business Server 2015 または Skype for Business Server ユーザーを実行しているサーバーをホストするドメインを準備するには、「セットアップを使用してドメインの準備を実行する」の説明に従って、手順 5: 現在のドメインを準備する必要があります。 この手順を完了するには、準備するドメインの Domain Admins グループのメンバー、またはドメインが属するフォレストの Enterprise Admins グループのメンバーとしてログインする必要があります。 ドメインを準備するには、以下の操作を行います。'
ms.openlocfilehash: b43af552983a5a7aae998fab6de9ace4e96084b2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804967"
---
# <a name="prepare-current-domain"></a>現在のドメインの準備

Skype for Business Server 2015 または Skype for Business Server ユーザーを実行しているサーバーをホストするドメインを準備するには、「セットアップを使用してドメインの準備を実行する」の説明に従って、手順 **5:** 現在のドメインを準備する必要 [があります。](https://technet.microsoft.com/library/95dab800-1f2c-4506-b36c-99986643b149.aspx) この手順を完了するには、準備するドメインの Domain Admins グループのメンバー、またはドメインが属するフォレストの Enterprise Admins グループのメンバーとしてログインする必要があります。 ドメインを準備するには、以下の操作を行います。

1. Skype for Business Server 2015 インストール フォルダーまたはメディアから Setup.exe Skype for Business Server 展開ウィザードを起動します。

2. [**Active Directory の準備**] をクリックし、展開状態が判別されるまで待ちます。

3. [**手順 5: 現在のドメインの準備**] で、[**実行**] をクリックします。

4. [**コマンドを実行しています**] ページで [**タスク状態: 完了**] を見つけて、[**ログの表示**] をクリックします。

5. [操作 **]** 列で[ **ドメイン** の準備] を展開し、各タスクの最後に実行結果を探して、ドメインの準備が正常に完了したのを確認し、ログを閉じて、[完了] を **\<Success\>** クリック **します**。

> [!TIP]
> Skype for Business Server 展開ウィザードで作成されたログ ファイルを確認する必要がある場合は、展開ウィザードが実行されたコンピューターの手順を実行した Active Directory ドメイン サービス ユーザーの Users ディレクトリでログ ファイルを見つける必要があります。 たとえば、ユーザーがドメイン Contoso.net でドメイン管理者としてログインした場合、ログ ファイルは C:\Users\Administrator.Contoso\AppData\Local\Temp にあります。


