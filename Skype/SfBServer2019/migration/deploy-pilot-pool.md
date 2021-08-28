---
title: パイロット プールの展開
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
description: 2019 年から 2019 年に移行するためにSkype for Business Server手順の 1 つは、パイロット プールを展開する方法です。 パイロット プールは、従来の展開と 2019 Skype for Business Serverの共存をテストする場所です。 共存は、すべてのユーザーとプールを 2019 年に移動するまでSkype for Business Serverです。
ms.openlocfilehash: e69e42e95ce7d13d8da88e91d6f1c266d7449f7b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58614991"
---
# <a name="deploy-skype-for-business-server-2019-pilot-pool"></a>2019 Skype for Business Serverパイロット プールの展開

2019 年から 2019 年に移行するためにSkype for Business Server手順の 1 つは、パイロット プールを展開する方法です。 パイロット プールは、従来の展開と 2019 Skype for Business Serverの共存をテストする場所です。 共存は、すべてのユーザーとプールを 2019 年に移動するまでSkype for Business Serverです。 
  
パイロット プールを展開するときには、新しいフロントエンド プールの定義ウィザードを使用します。 従来のプールにある 2019 パイロット プールSkype for Business Server同じ機能とワークロードを展開する必要があります。 従来の環境をアーカイブまたは監視するためにアーカイブ サーバー、監視サーバー、または System Center Operations Manager を展開し、移行全体を通じてアーカイブまたは監視を続行する場合は、パイロット環境にもこれらの機能を展開する必要があります。 従来の環境をアーカイブまたは監視するために展開したバージョンでは、2019 環境でデータSkype for Business Serverされません。 
  
> [!NOTE]
> 次の手順では、パイロット プール全体の展開プロセスの中で検討する必要がある機能と設定について説明します。 このセクションで説明するのは、パイロット プールの展開の際に考慮が必要となる主なポイントのみです。 <!-- For detailed steps, refer to the 
 [Deploying Skype for Business Server 2019](../deployment/deploying-lync-server-2013/deploying-lync-server-2013.md) deployment guide.  -->
  
### <a name="to-deploy-a-skype-for-business-server-2019-pilot-pool"></a>2019 パイロット Skype for Business Serverを展開するには

1. トポロジ ビルダーがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。
    
2. **2019 年 2019** 年Skype for Business Serverまでツリー Enterprise Edition  >  **展開します**。
    
3. [フロント エンド プールEnterprise Edition **右クリックし、[** 新しい **フロント エンド プール] を選択します**。
  
4. プールの完全修飾ドメイン名 (FQDN) を入力します。 パイロット プールを定義する場合は、フロントエンド プールまたはEnterprise Editionサーバーを展開Standard Editionできます。 Skype for Business Server 2019 では、パイロット プールの機能が従来のプールに展開された機能と一致する必要があります。
    
    > [!CAUTION]
    > パイロット プール用に定義するプールまたはサーバーの FQDN は一意である必要があります。 現在展開されているレガシ プールまたは現在展開されている他のサーバーの名前と一致しません。 
  
5. **[機能の選択]** ページで、このフロント エンド プールで必要な機能のチェック ボックスをオンにします。 たとえば、インスタント メッセージング (IM) とプレゼンス機能のみを展開する場合は、[会議] チェック ボックスをオンにしてマルチパーティ IM を許可しますが、音声、ビデオ、およびコラボレーション会議機能を表すダイヤルイン (PSTN) 会議、エンタープライズ VoIP、通話受付管理の各チェック ボックスは選択しない場合があります。 <!-- For additional information on selecting features, see 
 [Define and configure a Front End pool or Standard Edition server in Skype for Business Server 2019](../deployment/deploying-lync-server-2013/define-and-configure-a-front-end-pool-or-standard-edition-server.md) in the Deployment documentation.  -->
  
6. [サーバー **の役割の選択**] ページで、2019 年に仲介サーバーをSkype for Business Serverすることをお勧めします。 従来のトポロジを 2019 年 2019 年Skype for Business Serverする場合は、最初にレガシ 仲介サーバーを併合する必要があります。 トポロジをマージして Skype for Business Server 2019 仲介サーバーを構成した後、展開プロセスの後半で仲介サーバーの役割を Skype for Business Server 2019 に移動するときに、併置された仲介サーバーを保持するか、スタンドアロン サーバーに変更するかどうかを決定できます。 
   
7. [サーバー **の役割を** このフロントエンド プールに関連付ける] ページで、パイロット プールの展開中に、[このフロントエンド プールのメディア コンポーネントで使用するエッジ プールを有効にする] オプション **を選択** しません。 これは、移行のフェーズが進んだ段階で有効にしてオンラインにする機能です。 現時点ではこの設定はオフのままにしてください。 
  
8. [**Office Web Apps Server の選択**] ページで [**新規作成**] をクリックし、アプリケーション サーバーの FQDN を指定します。
  
9. [アーカイブSQL Server ストアの定義] ページで、Skype for Business Server アーカイブと監視の両方の SQL Server ストアを定義する場合は、Skype for Business Server 2019 用に前に作成した SQL Server インスタンスを選択します。 
  
10. トポロジを発行するには、[トポロジ] ノードを **右** クリックSkype for Business Server、[トポロジの公開]**をクリックします**。
  
11. 公開プロセスが完了したら、[**完了**] をクリックします。

12. 「従来のプールとのパイロット プールの共存を確認する」という次のセクションに移動する前に、公開トポロジで定義した Skype for Business Server 新しいフロントエンド パイロット プールをインストールする必要があります。トポロジ内のサーバーに[Skype for Business Server](../../SfbServer/deploy/install/install-skype-for-business-server.md)をインストールするで説明する手順に従ってください。

13. 前の手順が完了したら、[パイロット プールとレガシ プールとの共存を確認する] の次のセクションに移動します。
    
<!-- To install a local copy of the configuration store and start the required services, see 
[Setting up Front End Servers and Front End pools for Skype for Business Server 2019](../deployment/deploying-lync-server-2013/setting-up-front-end-servers-and-front-end-pools.md) in the Deployment documentation.  -->
