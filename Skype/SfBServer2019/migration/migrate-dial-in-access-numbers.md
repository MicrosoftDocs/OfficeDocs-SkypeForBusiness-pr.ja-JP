---
title: ダイヤルイン アクセス番号を移行する
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: ダイヤルインアクセス番号を Skype for Business Server 2019 に移行するには、連絡先オブジェクトを移行するために、Move-CsApplicationEndpoint コマンドレットを実行する必要があります。 従来のインストールと Skype for business Server 2019 の共存期間の間、このセクションで説明するように、Skype for Business Server 2019 で作成したダイヤルインアクセス番号は、従来のインストールで作成したダイヤルインアクセス番号と同じように動作します。
ms.openlocfilehash: 0df71debe8a6d5c686d8bce17b837f32a4ca2bab
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752699"
---
# <a name="migrate-dial-in-access-numbers"></a>ダイヤルイン アクセス番号を移行する

ダイヤルインアクセス番号を Skype for Business Server 2019 に移行するには、連絡先オブジェクトを移行するために、 **Move-CsApplicationEndpoint**コマンドレットを実行する必要があります。 従来のインストールと Skype for business Server 2019 の共存期間の間、このセクションで説明するように、Skype for Business Server 2019 で作成したダイヤルインアクセス番号は、従来のインストールで作成したダイヤルインアクセス番号と同じように動作します。 

従来のインストールで作成したが Skype for business Server 2019 に移動したダイヤルインアクセス番号、または移行前、移行中、または移行後に Skype for Business Server 2019 で作成したダイヤルインアクセス番号には、次のような特徴があります。

- Office Communications Server 2007 R2 の会議への招待およびダイヤルインアクセス番号ページには表示されません。

- [従来の会議出席依頼のインストールとダイヤルインアクセス番号] ページに表示されます。

- Skype for Business Server 2019 の会議への招待およびダイヤルインアクセス番号ページに表示されます。

- Office Communications Server 2007 R2 管理ツールで表示または変更することはできません。

- レガシーインストールコントロールパネルと従来のインストール管理シェルで表示および変更できます。

- Skype for Business Server 2019 コントロールパネルおよび Skype for Business Server 2019 管理シェルで表示および変更できます。

- Set-CsDialinConferencingAccessNumber コマンドレットで Priority パラメーターを指定して、地域内で並べ直すことができます。

従来のインストールプールを使用停止にする前に、従来のインストールプールをポイントするダイヤルインアクセス番号の移行を完了する必要があります。 記載されている以下の手順でダイヤルイン アクセス番号の移行を完了しないと、そのアクセス番号への着信通話が失敗します。

> [!IMPORTANT]
> 従来のインストールプールを使用停止にする前に、この手順を実行する必要があります。 

> [!NOTE]
> サービスが短時間停止される場合に備えて、ネットワークの使用率が低いときに、ダイヤルイン アクセス番号を移動することをお勧めします。 

## <a name="to-identify-and-move-dial-in-access-numbers"></a>ダイヤルイン アクセス番号を識別し、移動するには

1. Skype for Business Server 管理シェルを起動します。 [**スタート**]、[**すべてのプログラム**]、[ **Microsoft Skype for business Server 2019**]、[ **skype for business server 管理シェル**] の順にクリックします。

2. 各ダイヤルインアクセス番号を Skype for Business Server 2019 でホストされているプールに移動するには、コマンドラインで次のコマンドを実行します。 

   ```PowerShell
   Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>
   ```

3. Skype for Business Server コントロールパネルを開きます。

4. 左側のナビゲーション バーで **[会議]** をクリックします。

5. [**ダイヤルインアクセス番号**] タブをクリックします。 

6. 移行元の従来のインストールプールに対して、ダイヤルインアクセス番号が残っていないことを確認します。

    > [!NOTE]
    > すべてのダイヤルインアクセス番号が Skype for Business Server 2019 プールをポイントしている場合は、従来のインストールプールを使用停止にすることができます。 

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-control-panel"></a>Skype for Business Server コントロールパネルを使用してダイヤルインアクセス番号の移行を確認する

1. **Csuseradministrator**または**csadministrator**の役割に割り当てられているユーザーアカウントから、内部展開の任意のコンピューターにログオンします。 

2. Skype for Business Server コントロールパネルを開きます。

3. 左側のナビゲーション バーで **[会議]** をクリックします。

4. [**ダイヤルインアクセス番号**] タブをクリックします。 

5. すべてのダイヤルインアクセス番号が Skype for Business Server 2019 でホストされているプールに移行されることを確認します。

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-management-shell"></a>Skype for Business Server 管理シェルを使用してダイヤルインアクセス番号の移行を確認する

1. Skype for Business Server 管理シェルを開きます。

2. 移行されたすべてのダイヤルイン会議アクセス番号を戻すには、コマンドラインで次のコマンドを実行します。

   ```PowerShell
   Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}
   ```

3. すべてのダイヤルインアクセス番号が Skype for Business Server 2019 でホストされているプールに移行されることを確認します。


