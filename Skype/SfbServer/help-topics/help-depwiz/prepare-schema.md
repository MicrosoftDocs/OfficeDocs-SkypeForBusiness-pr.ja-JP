---
title: スキーマの準備
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
- ms.lync.dep.DeployMainSchemaPrep
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 337aa234-c5f3-4468-a047-2023848e942c
description: Active Directory ドメイン サービスのスキーマを準備するには、展開ウィザードの [スキーマの準備] Skype for Business Server実行します。 [実行] をクリックしてスキーマの準備を開始します。 [スキーマの準備] 手順では、展開ウィザードが実行されているシステムの /Program Files/Microsoft Lync Server 2013/Deployment/Setup ディレクトリ内の指定されたスキーマ定義ファイルを読み取ります。 これらのファイルは、サポート/スキーマ ディレクトリのインストール メディアでも使用できます。 [スキーマの準備] 手順では、スキーマを拡張し、プロセスの状態を報告します。 また、プロセスが完了したことも通知します。 概要画面では、プロセスのログを表示できます。 ログを調べ、正常に準備が完了したことを確認してください。
ms.openlocfilehash: 3adc63ec8eaa16b4eaebe528508f1f063e9cd7b5
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58612566"
---
# <a name="prepare-schema"></a>スキーマの準備
 
Active Directory ドメイン サービスのスキーマを準備するには、展開ウィザードの [スキーマの準備] Skype for Business Server実行します。 **[実行]** をクリックしてスキーマの準備を開始します。 [スキーマの準備] 手順では、展開ウィザードが実行されているシステムの \Program Files\Microsoft Lync Server 2013\Deployment\Setup ディレクトリにある指定されたスキーマ定義ファイルを読み取ります。 これらのファイルは、インストール メディアの \Support\Schema ディレクトリにもあります。 [スキーマの準備] 手順では、スキーマを拡張し、プロセスの状態を報告します。 また、プロセスが完了したことも通知します。 概要画面では、プロセスのログを表示できます。 ログを調べ、正常に準備が完了したことを確認してください。
  
> [!IMPORTANT]
> スキーマを拡張するには、Schema Admins グループおよび Enterprise Admins グループのメンバーとしてドメインにログインする必要があります。 
  
クラスと属性が追加され、Active Directory ドメイン サービス スキーマが拡張され、2015 Skype for Business Server、サービス、およびユーザー オブジェクトがサポートされます。 スキーマを拡張する前に、スキーマ マスター役割を持つドメイン コントローラーのシステム状態バックアップを行ってください。 SP1 を使用したサーバー 2008 R2 Windowsのバックアップ プロセスの詳細については、を参照してください [https://go.microsoft.com/fwlink/p/?linkId=207198](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee849849(v=ws.10)) 。 サーバー 2003 Windowsおよびサーバー 2003 R2 Windowsについては、を参照してください [https://go.microsoft.com/fwlink/p/?linkId=207199](/previous-versions/windows/it-pro/windows-server-2003/cc787254(v=ws.10)) 。
  
> [!CAUTION]
> スキーマの拡張は元に戻すことはできません。 スキーマ拡張が失敗した場合の潜在的な影響を抑制するためにあらゆる手段を講じ、スキーマの拡張が成功するようにしてください。 これは、通信が途絶えた場合や、サーバーでその他の障害が発生した場合には特に重要です。 スキーマ マスター ドメイン コントローラーのバックアップと Active Directory の完全なバックアップを実行する必要があります。 
  
スキーマ マスター ドメイン コントローラーのバックアップと Active Directory の完全なバックアップを実行するには、次の手順を実行します。
  
1. スキーマ マスター役割を持つドメイン コントローラーをネットワークから切断します。
    
2. スキーマ マスターを保持するドメイン コントローラーのシステム状態バックアップを実行します。
    
3. スキーマを拡張します。
    
4. スキーマを正常に拡張できたら、ドメイン コントローラーをネットワークに再接続し、レプリケーションがアクティブで機能していることを確認します。
    
5. スキーマ拡張機能に障害が発生した場合は、前に行った System State バックアップを使用して、ドメイン コントローラーと Active Directory のシステム状態を復元します。
    
> [!NOTE]
> Skype for Business Server 展開ウィザードによって作成されたログ ファイルを確認する必要がある場合は、展開ウィザードが実行されたコンピューター上のファイルを、手順を実行した Active Directory ユーザーの Users ディレクトリにあります。 たとえば、ユーザーがドメイン Contoso.net でドメイン管理者としてログインした場合、ログ ファイルは C:\Users\Administrator.Contoso\AppData\Local\Temp にあります。 
