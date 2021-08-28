---
title: 現在のドメインの準備
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainDomainPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: bfcb37ca-34eb-4d0d-9694-6edd2e7fe0f3
ROBOTS: NOINDEX, NOFOLLOW
description: 'Skype for Business Server または Skype for Business Server ユーザーを実行しているサーバーをホストするドメインを準備するには、「セットアップを使用してドメイン準備を実行する」のトピックで説明されている手順 5: 現在のドメインの準備を完了する必要があります。 この手順を完了するには、準備するドメインの Domain Admins グループのメンバー、またはドメインが属するフォレストの Enterprise Admins グループのメンバーとしてログインする必要があります。 ドメインを準備するには、以下の操作を行います。'
ms.openlocfilehash: 74725bde4f50219a2d46cca4ab0ab32daa733b83
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58616913"
---
# <a name="prepare-current-domain"></a>現在のドメインの準備

Skype for Business Server または Skype for Business Server ユーザーを実行しているサーバーをホストするドメインを準備するには、「セットアップを使用してドメイン準備を実行する」のトピックで説明されている手順 **5:** Prepare Current Domain を完了 [する必要があります](/previous-versions/office/lync-server-2013/lync-server-2013-running-domain-preparation)。 この手順を完了するには、準備するドメインの Domain Admins グループのメンバー、またはドメインが属するフォレストの Enterprise Admins グループのメンバーとしてログインする必要があります。 ドメインを準備するには、以下の操作を行います。

1. インストール フォルダー Skype for Business Serverメディアから、インストール フォルダーをSetup.exe展開ウィザードをSkype for Business Serverします。

2. [**Active Directory の準備**] をクリックし、展開状態が判別されるまで待ちます。

3. [**手順 5: 現在のドメインの準備**] で、[**実行**] をクリックします。

4. [**コマンドを実行しています**] ページで [**タスク状態: 完了**] を見つけて、[**ログの表示**] をクリックします。

5. [ **アクション] 列で** 、[ **ドメイン** 準備] を展開し、各タスクの最後に実行結果を探して、ドメイン準備が正常に完了したと確認し、ログを閉じて、[完了] **\<Success\>** をクリック **します**。

> [!TIP]
> Skype for Business Server 展開ウィザードによって作成されたログ ファイルを確認する必要がある場合は、展開ウィザードが実行されたコンピューターで、手順を実行した Active Directory ドメイン サービス ユーザーの Users ディレクトリで確認できます。 たとえば、ユーザーがドメイン Contoso.net でドメイン管理者としてログインした場合、ログ ファイルは C:\Users\Administrator.Contoso\AppData\Local\Temp にあります。