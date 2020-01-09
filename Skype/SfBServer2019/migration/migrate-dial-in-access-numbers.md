---
title: ダイヤルイン アクセス番号の移行
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype for Business Server 2019 にダイヤルインアクセス番号を移行するには、Move-CsApplicationEndpoint コマンドレットを実行して、連絡先オブジェクトを移行する必要があります。 従来のインストールと Skype for Business Server 2019 の共存期間の間、Skype for Business Server 2019 で作成したダイヤルインアクセス番号は、この後で説明するように、従来のインストールで作成したダイヤルインアクセス番号と同じように動作します。ここ.
ms.openlocfilehash: 35c1e665f8affdbf84628f9a7d532405779648f0
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991142"
---
# <a name="migrate-dial-in-access-numbers"></a>ダイヤルイン アクセス番号の移行

Skype for Business Server 2019 にダイヤルインアクセス番号を移行するには、 **Move-CsApplicationEndpoint**コマンドレットを実行して、連絡先オブジェクトを移行する必要があります。 従来のインストールと Skype for Business Server 2019 の共存期間の間、Skype for Business Server 2019 で作成したダイヤルインアクセス番号は、この後で説明するように、従来のインストールで作成したダイヤルインアクセス番号と同じように動作します。ここ. 

従来のインストールで作成したが、Skype for Business Server 2019 に移動したか、移行中、または移行後に Skype for Business Server 2019 で作成したダイヤルインアクセス番号には、次の特徴があります。

- Office Communications Server 2007 R2 会議の出席依頼とダイヤルインアクセス番号のページには表示されません。

- 従来の [会議出席依頼のインストールとダイヤルインアクセス番号] ページに表示されます。

- Skype for Business Server 2019 の会議出席依頼とダイヤルインアクセス番号のページに表示されます。

- Office Communications Server 2007 R2 管理ツールでは、表示または変更できません。

- 従来の [コントロールパネル] の [レガシーインストールの管理] シェルで、表示と変更ができます。

- Skype for Business Server 2019 コントロールパネルと Skype for Business Server 2019 Management Shell で表示および変更できます。

- Priority パラメーターを指定して CsDialinConferencingAccessNumber コマンドレットを使用して、地域内で再シーケンスできます。

レガシインストールプールを廃止する前に、以前のインストールプールを参照するダイヤルインアクセス番号の移行を完了する必要があります。 次の手順で説明するように、ダイヤルインアクセス番号の移行が完了していない場合は、アクセス番号への着信通話が失敗します。

> [!IMPORTANT]
> レガシインストールプールを廃止する前に、この手順を実行する必要があります。 

> [!NOTE]
> 短時間のサービス停止が発生した場合に備えて、ネットワーク使用量が少ない場合は、ダイヤルインアクセス番号を移動することをお勧めします。 

## <a name="to-identify-and-move-dial-in-access-numbers"></a>ダイヤルインアクセス番号を特定して移動するには

1. Skype for Business Server 管理シェルを開始します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft skype for business Server 2019**]、[ **skype for business server 管理シェル**] の順にクリックします。

2. Skype for Business Server 2019 でホストされているプールにダイヤルインアクセス番号を移動するには、コマンドラインで次を実行します。 

   ```PowerShell
   Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>
   ```

3. Skype for Business Server コントロールパネルを開きます。

4. 左側のナビゲーション バーで [**会議**] をクリックします。

5. [**ダイヤルインアクセス番号**] タブをクリックします。 

6. 移行元のレガシーインストールプールのダイヤルインアクセス番号が残っていないことを確認します。

    > [!NOTE]
    > すべてのダイヤルインアクセス番号が Skype for Business Server 2019 プールをポイントしている場合、レガシインストールプールを廃止することができます。 

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-control-panel"></a>Skype for Business Server コントロールパネルを使用して、ダイヤルインアクセス番号の移行を確認する

1. **Csuseradministrator**ロールまたは**csadministrator**ロールに割り当てられているユーザーアカウントから、社内展開の任意のコンピューターにログオンします。 

2. Skype for Business Server コントロールパネルを開きます。

3. 左側のナビゲーション バーで [**会議**] をクリックします。

4. [**ダイヤルインアクセス番号**] タブをクリックします。 

5. すべてのダイヤルインアクセス番号が、Skype for Business Server 2019 でホストされているプールに移行されていることを確認します。

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-management-shell"></a>Skype for Business Server 管理シェルを使用したダイヤルインアクセス番号の移行を確認する

1. Skype for Business Server 管理シェルを開きます。

2. 移行されたダイヤルイン会議アクセス番号をすべて返すには、コマンドラインで次を実行します。

   ```PowerShell
   Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}
   ```

3. すべてのダイヤルインアクセス番号が、Skype for Business Server 2019 でホストされているプールに移行されていることを確認します。


