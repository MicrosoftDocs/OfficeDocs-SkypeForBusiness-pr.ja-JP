---
title: パイロット プールの展開
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype for Business Server 2019 への移行に必要な最初の手順の1つは、パイロットプールを展開することです。 パイロットプールでは、Skype for Business Server 2019 と従来の展開を共存させることができます。 [共存] は、すべてのユーザーとプールを Skype for Business Server 2019 に移動するまで継続して使用できます。
ms.openlocfilehash: 3642d603b5923a554b8eca41a948125ef25526ae
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280865"
---
# <a name="deploy-skype-for-business-server-2019-pilot-pool"></a>Skype for Business Server 2019 パイロットプールの展開

Skype for Business Server 2019 への移行に必要な最初の手順の1つは、パイロットプールを展開することです。 パイロットプールでは、Skype for Business Server 2019 と従来の展開を共存させることができます。 [共存] は、すべてのユーザーとプールを Skype for Business Server 2019 に移動するまで継続して使用できます。 
  
パイロットプールを展開する場合は、[新しいフロントエンドプールの定義] ウィザードを使います。 Skype for Business Server 2019 パイロットプールで、従来のプールにあるものと同じ機能とワークロードを展開する必要があります。 アーカイブサーバー、監視サーバー、または System Center Operations Manager を展開して従来の環境をアーカイブまたは監視する場合、移行後もアーカイブまたは監視を継続するには、次の機能もに展開する必要があります。パイロット環境。 従来の環境をアーカイブまたは監視するために展開したバージョンでは、Skype for Business Server 2019 環境のデータは取得されません。 
  
> [!NOTE]
> 次の手順では、パイロットプールの全体的な展開プロセスの一部として考慮する必要がある機能と設定について説明します。 このセクションでは、パイロットプールの展開の一部として考慮する必要がある重要なポイントについて説明します。 <!-- For detailed steps, refer to the 
 [Deploying Skype for Business Server 2019](../deployment/deploying-lync-server-2013/deploying-lync-server-2013.md) deployment guide.  -->
  
### <a name="to-deploy-a-skype-for-business-server-2019-pilot-pool"></a>Skype for Business Server 2019 パイロットプールを展開するには

1. トポロジ ビルダーがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。
    
2. **Skype for business Server 2019** > **Enterprise Edition のフロントエンドプール**に到達するまでツリーを展開します。
    
3. **Enterprise Edition のフロントエンドプール**を右クリックし、[**新しいフロントエンドプール**] を選択します。
  
4. プールの完全修飾ドメイン名 (FQDN) を入力します。 パイロットプールを定義する場合は、Enterprise Edition のフロントエンドプールまたは Standard Edition サーバーを展開することを選択できます。 Skype for Business Server 2019 では、パイロットプールの機能が、従来のプールに展開されたものと一致する必要はありません。
    
    > [!CAUTION]
    > パイロットプールに対して定義するプールまたはサーバーの FQDN は一意である必要があります。 現在展開されているレガシープールまたは現在展開されている他のサーバーの名前と一致させることはできません。 
  
5. **[機能の選択**] ページで、このフロントエンドプールに必要な機能のチェックボックスをオンにします。 たとえば、インスタントメッセージング (IM) とプレゼンス機能のみを展開している場合、[会議] チェックボックスをオンにして、マルチパーティ IM を許可しますが、ダイヤルイン (PSTN) 会議、エンタープライズボイス、または通話受付制御のチェックを選択することはできません。ボックス。音声、ビデオ、および共同作業の会議機能を表します。 <!-- For additional information on selecting features, see 
 [Define and configure a Front End pool or Standard Edition server in Skype for Business Server 2019](../deployment/deploying-lync-server-2013/define-and-configure-a-front-end-pool-or-standard-edition-server.md) in the Deployment documentation.  -->
  
6. **[併置**されたサーバーの役割の選択] ページで、Skype For business server 2019 で仲介サーバーを検索することを選択することをお勧めします。 Skype for Business Server 2019 で従来のトポロジを統合する場合、最初に従来の仲介サーバーを検索する必要があります。 トポロジをマージして、Skype for Business Server 2019 仲介サーバーを構成した後、仲介サーバーの役割を Skype for Business Server に移行するときに、併置された仲介サーバーを保持するか、スタンドアロンサーバーに変更するかを決定することができます。2019は、展開プロセスで後で実行します。 
   
7. パイロットプールの展開中に、[**サーバーの役割をこのフロントエンドプールに関連付ける**] ページで、[**このフロントエンドプールのメディアコンポーネントで使用するエッジプールを有効**にする] オプションを選択しないで*ください*。 これは、移行の後のフェーズで有効にしてオンラインにする機能です。 ここでは、この設定をオフのままにしておきます。 
  
8. [ **Office Web Apps サーバーを選択**してください] ページで、[**新規**] をクリックし、アプリケーションサーバーの FQDN を指定します。
  
9. [**アーカイブ SQL server ストアの定義**] ページで、skype For business Server のアーカイブと監視の両方のために sql server ストアを定義する場合は、以前に skype For business server 2019 用に作成した sql server インスタンスを選びます。 
  
10. トポロジを公開するには、[ **Skype For Business Server** ] ノードを右クリックし、[**トポロジの公開**] をクリックします。
  
11. 発行プロセスが完了したら、[**完了**] をクリックします。

12. "パイロットプールとレガシプールを共存させる" という名前の次のセクションに移動する前に、「Skype for Business Server」で説明している手順に従って、「Skype for business をインストールする」を参照してください。 [トポロジ内のサーバー上のビジネスサーバー](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)

13. 前の手順が完了したら、次のセクションに進んで、パイロットプールとレガシプールを共存させることができます。
    
<!-- To install a local copy of the configuration store and start the required services, see 
[Setting up Front End Servers and Front End pools for Skype for Business Server 2019](../deployment/deploying-lync-server-2013/setting-up-front-end-servers-and-front-end-pools.md) in the Deployment documentation.  -->
  

