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
description: 'ドメインの準備手順 1 で実行のレプリケーションを確認する: スキーマの準備、Skype からビジネス サーバー管理シェル Lync Server 管理シェルのコマンドレットを実行する必要があります。 Windows PowerShell コマンドレットを実行するには、Domain Admins グループのメンバーと、準備したドメインのメンバーであるコンピューターにログオンします。 次の操作を実行します。'
ms.openlocfilehash: 8577c3c1e40744154fba8ef886220daf441970b8
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/20/2018
ms.locfileid: "19974804"
---
# <a name="verify-replication-in-the-domain"></a>ドメイン内のレプリケーションの確認
 
ドメインの準備の実行のレプリケーションを確認するのには**ステップ 1: スキーマの準備**、Skype からビジネス サーバー管理シェル Lync Server 管理シェルのコマンドレットを実行する必要があります。 Windows PowerShell コマンドレットを実行するには、Domain Admins グループのメンバーと、準備したドメインのメンバーであるコンピューターにログオンします。 次の操作を実行します。
  
1. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
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
    

