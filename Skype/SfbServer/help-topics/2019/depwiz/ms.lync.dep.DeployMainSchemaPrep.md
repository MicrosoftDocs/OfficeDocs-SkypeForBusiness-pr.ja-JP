---
title: スキーマの準備
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainSchemaPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 337aa234-c5f3-4468-a047-2023848e942c
ROBOTS: NOINDEX, NOFOLLOW
description: Active Directory ドメイン サービスのスキーマを準備するのにはビジネス サーバーの展開ウィザードは、Skype で、スキーマの準備の手順を実行します。 [実行] をクリックしてスキーマの準備を開始します。
ms.openlocfilehash: 6a1290560ea5d10891b3878732aef2bdf85ae17d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33893666"
---
# <a name="prepare-schema"></a>スキーマの準備
 
Active Directory ドメイン サービスのスキーマを準備するのにはビジネス サーバーの展開ウィザードは、Skype で、スキーマの準備の手順を実行します。 [**実行**] をクリックしてスキーマの準備を開始します。 スキーマの準備の手順は、定義ファイル、\Program Files\Skype のビジネス サーバーの 2019\Deployment\Setup ディレクトリにで展開ウィザードが実行されているシステムで指定されたスキーマを読み取ります。 これらのファイルは、インストール メディアの \Support\Schema ディレクトリにもあります。 [スキーマの準備] 手順では、スキーマを拡張し、プロセスの状態を報告します。 また、プロセスが完了したことも通知します。 概要画面では、プロセスのログを表示できます。 ログを調べ、正常に準備が完了したことを確認してください。
  
> [!IMPORTANT]
> スキーマを拡張するには、Schema Admins グループおよび Enterprise Admins グループのメンバーとしてドメインにログインする必要があります。 
  
ビジネス サーバーのサーバー、サービス、およびユーザー オブジェクトの Skype をサポートするために Active Directory ドメイン サービス スキーマを拡張するクラスおよび属性が追加されます。 スキーマを拡張する前に行う必要があるシステムの状態、スキーマ マスターの役割を保持しているドメイン コント ローラーのバックアップを作成します。 
  
> [!CAUTION]
> スキーマの拡張は元に戻すことはできません。 スキーマ拡張が失敗した場合の潜在的な影響を抑制するためにあらゆる手段を講じて、スキーマの拡張が成功するようにしてください。 これは、通信が途絶えた場合や、サーバーでその他の障害が発生した場合には特に重要です。 スキーマ マスター ドメイン コント ローラーのバックアップとアクティブなディレクトリの完全なバックアップを実行する必要があります。 
  
スキーマ マスター ドメイン コント ローラーのバックアップおよび Active Directory の完全なバックアップを実行するには。
  
1. スキーマ マスターの役割を持つドメイン コントローラーをネットワークから切断します。
    
2. スキーマ マスターを保持するドメイン コントローラーのシステム状態のバックアップを実行します。
    
3. スキーマを拡張します。
    
4. スキーマを正常に拡張できたら、ドメイン コントローラーをネットワークに再接続し、レプリケーションがアクティブで機能していることを確認します。
    
5. スキーマ拡張機能障害が万一、前述したシステム状態バックアップを使用してドメイン コント ローラーと Active Directory のシステム状態を復元します。
    
> [!NOTE]
> ビジネス サーバーの展開ウィザードは、Skype によって作成されるログ ファイルを確認する場合は、コンピューター上で、展開ウィザードが実行されたの手順を実行した Active Directory ユーザーのユーザー ディレクトリにファイルが表示されます。 たとえば、ユーザー Contoso.net のドメインのドメイン管理者としてログインしている場合、ログ ・ ファイル内にある: C:\Users\Administrator.Contoso\AppData\Local\Temp 
  

