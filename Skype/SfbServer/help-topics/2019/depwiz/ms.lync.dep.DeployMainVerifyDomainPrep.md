---
title: ドメイン内のレプリケーションの確認
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainVerifyDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4846b787-d55e-4364-bdcd-2dee33f0251c
ROBOTS: NOINDEX, NOFOLLOW
description: 'ドメインの準備手順 1 で実行のレプリケーションを確認する: スキーマの準備、Skype からビジネス サーバー管理シェル Lync Server 管理シェルのコマンドレットを実行する必要があります。 Windows PowerShell コマンドレットを実行するには、Domain Admins グループのメンバーと、準備したドメインのメンバーであるコンピューターにログオンします。 次の操作を実行します。'
ms.openlocfilehash: f5cf028cfb0957d339a2ac2a40a239f0c145a2c0
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "25373514"
---
# <a name="verify-replication-in-the-domain"></a>ドメイン内のレプリケーションの確認
 
ドメインの準備の実行のレプリケーションを確認するのには**ステップ 1: スキーマの準備**、Skype からビジネス サーバー管理シェル Lync Server 管理シェルのコマンドレットを実行する必要があります。 Windows PowerShell コマンドレットを実行するには、Domain Admins グループのメンバーと、準備したドメインのメンバーであるコンピューターにログオンします。 次の操作を実行します。
  
1. ビジネス サーバー管理シェルには、Skype を起動する: [**スタート**] ボタン、[**すべてのプログラム**] をクリックして、**ビジネスの Skype**をクリック**ビジネス サーバー管理シェルの Skype**です。
    
2. Windows PowerShell では、次のように入力します。
    
   ```
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    例:
    
   ```
   Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
   ```

    > [!NOTE]
    > パラメーター GlobalSettingsDomainController を使用して、グローバル設定を保存する場所を指定できます。 システム コンテナーではよくあるアップグレードの展開、構成コンテナーに移行したグローバル設定が行われていない) では、設定が保存されている場合、Active Directory ドメイン サービス フォレストのルート ドメイン コント ローラーを定義します。 グローバル設定を構成コンテナーに保存する (新しい展開または構成コンテナーに設定を移行しているアップグレードの展開で一般的) 場合、フォレストに任意のドメイン コントローラーを定義します。 このパラメーターを指定しない場合、コマンドレットでは、設定が構成コンテナーに保存されていると見なして、Active Directory の任意のドメイン コントローラーを参照します。 
  
    Domain パラメーターを指定しない場合、値はローカル ドメインに設定されます。 このコマンドレットでは、ドメインの準備が成功した場合、 **LC_DOMAIN_SETTINGS_STATE_READY**の値が返されます。
    

