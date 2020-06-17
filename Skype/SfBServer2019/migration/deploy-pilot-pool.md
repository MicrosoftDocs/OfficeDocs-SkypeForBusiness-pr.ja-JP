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
localization_priority: Normal
description: Skype for Business Server 2019 への移行に必要な最初の手順の1つは、パイロットプールを展開することです。 パイロットプールは、従来の展開と Skype for Business Server 2019 の共存をテストする場所です。 共存は、すべてのユーザーとプールを Skype for Business Server 2019 に移動するまで、一時的な状態になります。
ms.openlocfilehash: 46d8b6fd6cefa2894f67a1c24732ace01ca65785
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752859"
---
# <a name="deploy-skype-for-business-server-2019-pilot-pool"></a>Skype for Business Server 2019 パイロットプールの展開

Skype for Business Server 2019 への移行に必要な最初の手順の1つは、パイロットプールを展開することです。 パイロットプールは、従来の展開と Skype for Business Server 2019 の共存をテストする場所です。 共存は、すべてのユーザーとプールを Skype for Business Server 2019 に移動するまで、一時的な状態になります。 
  
パイロット プールを展開するときには、新しいフロントエンド プールの定義ウィザードを使用します。 従来のプールにある、Skype for Business Server 2019 パイロットプールと同じ機能とワークロードを展開する必要があります。 アーカイブサーバー、監視サーバー、または System Center Operations Manager を展開して従来の環境をアーカイブまたは監視している場合に、移行全体を通してアーカイブまたは監視を続行するには、これらの機能をパイロット環境に展開する必要があります。 従来の環境をアーカイブまたは監視するために展開したバージョンでは、Skype for Business Server 2019 環境のデータはキャプチャされません。 
  
> [!NOTE]
> 次の手順では、パイロット プール全体の展開プロセスの中で検討する必要がある機能と設定について説明します。 このセクションで説明するのは、パイロット プールの展開の際に考慮が必要となる主なポイントのみです。 <!-- For detailed steps, refer to the 
 [Deploying Skype for Business Server 2019](../deployment/deploying-lync-server-2013/deploying-lync-server-2013.md) deployment guide.  -->
  
### <a name="to-deploy-a-skype-for-business-server-2019-pilot-pool"></a>Skype for Business Server 2019 パイロットプールを展開するには

1. トポロジ ビルダーがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。
    
2. [ **Skype for business Server 2019**  >  **Enterprise Edition フロントエンドプール**] に到達するまでツリーを展開します。
    
3. [ **Enterprise Edition フロントエンドプール**] を右クリックし、[**新しいフロントエンドプール**] を選択します。
  
4. プールの完全修飾ドメイン名 (FQDN) を入力します。 パイロットプールを定義するときは、Enterprise Edition フロントエンドプールまたは Standard Edition サーバーを展開することを選択できます。 Skype for Business Server 2019 では、パイロットプールの機能が従来のプールに展開されたものと一致している必要はありません。
    
    > [!CAUTION]
    > パイロットプールに対して定義するプールまたはサーバーの FQDN は一意である必要があります。 現在展開されている従来のプールの名前、または現在展開されている他のすべてのサーバーの名前と一致することはできません。 
  
5. **[機能の選択]** ページで、このフロント エンド プールで必要な機能のチェック ボックスをオンにします。 たとえば、インスタントメッセージング (IM) とプレゼンス機能のみを展開する場合は、[会議] チェックボックスをオンにしてマルチパーティ IM を許可しますが、ダイヤルイン (PSTN) 会議、エンタープライズ Voip、または通話受付管理の各チェックボックスは、音声、ビデオ、および共同作業の会議機能を表すものであるため、選択しません。 <!-- For additional information on selecting features, see 
 [Define and configure a Front End pool or Standard Edition server in Skype for Business Server 2019](../deployment/deploying-lync-server-2013/define-and-configure-a-front-end-pool-or-standard-edition-server.md) in the Deployment documentation.  -->
  
6. [併置された**サーバーの役割の選択**] ページで、仲介サーバーを Skype For business server 2019 で併置することを選択することをお勧めします。 従来のトポロジを Skype for Business Server 2019 と統合する場合は、最初に従来の仲介サーバーを併置する必要があります。 トポロジをマージして、Skype for Business Server 2019 仲介サーバーを構成した後、展開プロセスで仲介サーバーの役割を Skype for Business Server 2019 に移動するときに、併置された仲介サーバーを保持するか、スタンドアロンサーバーに変更するかを決定することができます。 
   
7. [**サーバーの役割とこのフロントエンドプールの関連付け**] ページで、パイロットプールの展開時に [**このフロントエンドプールのメディアコンポーネントが使用するエッジプールを有効**にする] オプションを選択し*ません*。 これは、移行のフェーズが進んだ段階で有効にしてオンラインにする機能です。 現時点ではこの設定はオフのままにしてください。 
  
8. [**Office Web Apps Server の選択**] ページで [**新規作成**] をクリックし、アプリケーション サーバーの FQDN を指定します。
  
9. [**アーカイブ Sql server ストアの定義**] ページで、skype For business Server のアーカイブと監視の両方のために sql server ストアを定義する場合は、前の手順で skype For business server 2019 用に作成した sql server インスタンスを選択します。 
  
10. トポロジを公開するには、[ **Skype For Business Server** ] ノードを右クリックし、[**トポロジの公開**] をクリックします。
  
11. 公開プロセスが完了したら、[**完了**] をクリックします。

12. 「パイロットプールとレガシプールの共存を確認する」という名前の次のセクションに進む前に、「Skype for Business Server の新しいフロントエンドパイロットプールをインストールする必要があります。」で説明されている手順に従って、「[トポロジ内のサーバーに skype For Business server をインストール](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)する」を参照してください。

13. 前の手順が完了したら、次のセクションに移動して、従来のプールとパイロットプールが共存していることを確認します。
    
<!-- To install a local copy of the configuration store and start the required services, see 
[Setting up Front End Servers and Front End pools for Skype for Business Server 2019](../deployment/deploying-lync-server-2013/setting-up-front-end-servers-and-front-end-pools.md) in the Deployment documentation.  -->
  

