---
title: ダイヤルイン アクセス番号の移行
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: ダイヤルイン アクセス番号を 2019 年Skype for Business Server移行するには、連絡先オブジェクトを移行Move-CsApplicationEndpointコマンドレットを実行する必要があります。 従来のインストールと Skype for Business Server 2019 の共存期間中、Skype for Business Server 2019 で作成したダイヤルイン アクセス番号は、このセクションで説明するように、従来のインストールで作成したダイヤルイン アクセス番号と同様に動作します。
ms.openlocfilehash: 4d5d0ad88c241685e7ea86c7adc9dc536d3180a8
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58589337"
---
# <a name="migrate-dial-in-access-numbers"></a>ダイヤルイン アクセス番号の移行

ダイヤルイン アクセス番号を 2019 Skype for Business Serverに移行するには **、Move-CsApplicationEndpoint** コマンドレットを実行して連絡先オブジェクトを移行する必要があります。 従来のインストールと Skype for Business Server 2019 の共存期間中、Skype for Business Server 2019 で作成したダイヤルイン アクセス番号は、このセクションで説明するように、従来のインストールで作成したダイヤルイン アクセス番号と同様に動作します。 

従来のインストールで作成したが、Skype for Business Server 2019 に移動したダイヤルイン アクセス番号、または移行前、移行中、または移行後に Skype for Business Server 2019 で作成したダイヤルイン アクセス番号には、次の特性があります。

- コミュニケーション サーバー 2007 R2 Officeおよびダイヤルイン アクセス番号ページには表示されません。

- 従来の会議出席依頼のインストールとダイヤルイン アクセス番号ページに表示されます。

- 2019 Skype for Business Server会議出席依頼とダイヤルイン アクセス番号ページに表示されます。

- コミュニケーション サーバー 2007 R2 管理ツールOffice表示または変更できません。

- 従来のインストールコントロール パネルと従来のインストール管理シェルで表示および変更できます。

- 2019 コントロール パネルと 2019 管理Skype for Business Server 201 Skype for Business Server 9 管理シェルで表示および変更できます。

- Set-CsDialinConferencingAccessNumber コマンドレットで Priority パラメーターを指定して、地域内で並べ直すことができます。

レガシ インストール プールを使用停止する前に、レガシ インストール プールを指すダイヤルイン アクセス番号の移行を完了する必要があります。 記載されている以下の手順でダイヤルイン アクセス番号の移行を完了しないと、そのアクセス番号への着信通話が失敗します。

> [!IMPORTANT]
> 従来のインストール プールを使用停止する前に、この手順を実行する必要があります。 

> [!NOTE]
> サービスが短時間停止される場合に備えて、ネットワークの使用率が低いときに、ダイヤルイン アクセス番号を移動することをお勧めします。 

## <a name="to-identify-and-move-dial-in-access-numbers"></a>ダイヤルイン アクセス番号を識別し、移動するには

1. 管理シェルをSkype for Business Serverする: [スタート] をクリックし、[すべてのプログラム] をクリックし、[Microsoft Skype for Business Server **2019]** をクリックし、[管理シェルSkype for Business Server **クリックします**。

2. 各ダイヤルイン アクセス Skype for Business Server番号を 2019 年 2019 年にホストされているプールに移動するには、コマンド ラインから次のコマンドを実行します。 

   ```PowerShell
   Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>
   ```

3. [コントロール Skype for Business Server] を開きます。

4. 左側のナビゲーション バーで **[会議]** をクリックします。

5. [ダイヤル **イン アクセス番号] タブをクリック** します。 

6. 移行するレガシ インストール プールにダイヤルイン アクセス番号が残っていなか確認します。

    > [!NOTE]
    > すべてのダイヤルイン アクセス番号が 2019 年 2019 年のプールをポイントSkype for Business Server、従来のインストール プールを使用停止できます。 

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-control-panel"></a>[コントロール パネル] を使用してダイヤルイン アクセス番号Skype for Business Server確認する

1. **CsUserAdministrator** 役割または **CsAdministrator** 役割に割り当てられているユーザー アカウントから、内部展開内の任意のコンピューターにログオンします。 

2. [コントロール Skype for Business Server] を開きます。

3. 左側のナビゲーション バーで **[会議]** をクリックします。

4. [ダイヤル **イン アクセス番号] タブをクリック** します。 

5. すべてのダイヤルイン アクセス番号が 2019 年にホストされているプールに移行Skype for Business Serverします。

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-management-shell"></a>管理シェルを使用してダイヤルイン アクセス番号Skype for Business Server確認する

1. [管理Skype for Business Server] を開きます。

2. 移行されたすべてのダイヤルイン会議アクセス番号を返す場合は、コマンド ラインから次のコマンドを実行します。

   ```PowerShell
   Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}
   ```

3. すべてのダイヤルイン アクセス番号が 2019 年にホストされているプールに移行Skype for Business Serverします。


