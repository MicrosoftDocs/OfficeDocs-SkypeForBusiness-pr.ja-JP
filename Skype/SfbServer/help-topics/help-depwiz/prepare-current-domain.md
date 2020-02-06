---
title: 現在のドメインの準備
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
- ms.lync.dep.DeployMainDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bfcb37ca-34eb-4d0d-9694-6edd2e7fe0f3
description: 'Skype for Business Server 2015 または Skype for Business Server ユーザーを実行しているホストサーバーにドメインを準備するには、「セットアップを使用してドメインの準備を行う」の説明に従って、「手順 5: 現在のドメインを準備する」を完了する必要があります。 この手順を完了するには、準備するドメインの Domain Admins グループのメンバー、またはドメインが属するフォレストの Enterprise Admins グループのメンバーとしてログインする必要があります。 ドメインを準備するには、以下の操作を行います。'
ms.openlocfilehash: 2f3563c9a1c857e9d4828ca63cf2cb675f524e56
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823551"
---
# <a name="prepare-current-domain"></a>現在のドメインの準備

Skype for Business Server 2015 または Skype for Business Server ユーザーを実行しているホストサーバーにドメインを準備するには、「[セットアップを使用してドメインの準備を](https://technet.microsoft.com/library/95dab800-1f2c-4506-b36c-99986643b149.aspx)行う」の説明に従って、「**手順 5: 現在のドメインを準備**する」を完了する必要があります。 この手順を完了するには、準備するドメインの Domain Admins グループのメンバー、またはドメインが属するフォレストの Enterprise Admins グループのメンバーとしてログインする必要があります。 ドメインを準備するには、以下の操作を行います。

1. Skype for Business Server 2015 のインストールフォルダーまたはメディアから setup.exe を実行して、Skype for Business Server 展開ウィザードを開始します。

2. [**Active Directory の準備**] をクリックして、展開状態が判別されるまで待ちます。

3. [**手順 5: 現在のドメインの準備**] で、[**実行**] をクリックします。

4. [**コマンドの実行**] ページで [**タスク状態: 完了**] を見つけて、[**ログの表示**] をクリックします。

5. [**アクション**] 列で、[**ドメインの準備**] を展開し、各タスクの最後に** \<成功\> **の実行結果を探して、ドメインの準備が正常に完了したことを確認します。次に、[**完了**] をクリックします。

> [!TIP]
> Skype for Business Server 展開ウィザードによって作成されたログファイルを確認する必要がある場合は、この手順を実行した Active Directory ドメインサービスユーザーの Users ディレクトリで展開ウィザードが実行されたコンピューターで確認できます。 たとえば、ユーザーがドメイン Contoso.net のドメイン管理者としてログインしている場合、ログファイルは C:\Users\Administrator.Contoso\AppData\Local\Temp. にあります。


