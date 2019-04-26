---
title: パイロット プールの展開
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: パイロット プールを展開するビジネス サーバー 2019 の Skype への移行に必要な最初の手順のいずれかです。 パイロットのプールとは、従来の展開とビジネス サーバー 2019 の Skype の共存をテストします。 共存とは、移動したすべてのユーザーとプール Skype のビジネス サーバー 2019 まで存続する一時的な状態です。
ms.openlocfilehash: 26f391a485c991aa3575498b98b181f1b5ac761c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32238536"
---
# <a name="deploy-skype-for-business-server-2019-pilot-pool"></a>ビジネス サーバー 2019 パイロット プールに Skype を導入します。

パイロット プールを展開するビジネス サーバー 2019 の Skype への移行に必要な最初の手順のいずれかです。 パイロットのプールとは、従来の展開とビジネス サーバー 2019 の Skype の共存をテストします。 共存とは、移動したすべてのユーザーとプール Skype のビジネス サーバー 2019 まで存続する一時的な状態です。 
  
パイロット プールを展開するときは、新しいフロント エンド プールの定義ウィザードを使用します。 レガシ プール内にあるビジネス サーバー 2019 パイロット プールのため、Skype で同じ機能とワークロードを配置する必要があります。 アーカイブや、従来の環境を監視するためのアーカイブ サーバー、監視サーバー、または System Center Operations Manager を展開して、アーカイブまたは移行中の監視を継続する場合もこれらの機能を配置する必要があります、パイロット環境です。 アーカイブまたはレガシを監視するバージョンを展開した環境はサーバー 2019 のビジネス環境について、Skype でデータをキャプチャしていません。 
  
> [!NOTE]
> 次の手順では、機能と、プールの全体的なパイロット展開プロセスの一部として考慮する必要があります設定について説明します。 のみ、このセクションには、パイロット プール展開の一環として検討する必要がある重要なポイントが強調表示されます。 <!-- For detailed steps, refer to the 
 [Deploying Skype for Business Server 2019](../deployment/deploying-lync-server-2013/deploying-lync-server-2013.md) deployment guide.  -->
  
### <a name="to-deploy-a-skype-for-business-server-2019-pilot-pool"></a>Skype のビジネス サーバー 2019 パイロット プールを展開するには

1. トポロジ ビルダーがインストールされているコンピューターに、Domain Admins グループおよび RTCUniversalServerAdmins グループのメンバーとしてログオンします。
    
2. **ビジネス サーバー 2019 の Skype**に到達するまでツリーを展開し > **エンタープライズ エディションのフロント エンド プール**です。
    
3. **エンタープライズ エディションのフロント エンド プール**を右クリックし、**新しいフロント エンド プール**を選択します。
  
4. プールの完全修飾ドメイン名 (FQDN) を入力します。 パイロット プールを定義するとき、エンタープライズ エディションのフロント エンド プールまたは Standard Edition サーバーを展開することができます。 ビジネス サーバー 2019 の Skype では、レガシ プールに展開するとどのようなパイロットのプールの機能に一致する必要はありません。
    
    > [!CAUTION]
    > プールまたはサーバーの FQDN のパイロットのプールを定義することは、一意である必要があります。 展開済みの従来のプールまたは現在展開されているその他のサーバーの名前に対応します。 
  
5. [**機能の選択**] ページで、このフロント エンド プールで必要な機能のチェック ボックスを選択します。 インスタント メッセージング (IM) とプレゼンスの機能のみを配置する場合は、マルチパーティ IM を許可するのには、[会議] チェック ボックスを選択ですが、ダイヤルイン (PSTN) 会議、エンタープライズ VoIP を選択しないなど、受付制御の呼び出しをチェックボックス、音声、ビデオ、および共同作業の会議機能を表しているためです。 <!-- For additional information on selecting features, see 
 [Define and configure a Front End pool or Standard Edition server in Skype for Business Server 2019](../deployment/deploying-lync-server-2013/define-and-configure-a-front-end-pool-or-standard-edition-server.md) in the Deployment documentation.  -->
  
6. **ロールの配置されているサーバーの選択]** ページで、ビジネス サーバー 2019 の Skype に仲介サーバーを連結するように選択することをお勧めします。 ビジネス サーバー 2019 の Skype での従来のトポロジをマージするときに最初に従来の仲介サーバーに集約するが必要です。 トポロジをマージすると、Skype のビジネス 2019 仲介サーバーの構成、配置されている仲介サーバーを維持または Skype をビジネスのサーバーの仲介サーバーの役割を移動するときは、スタンドアロンのサーバーに変更するかどうか決定できます。展開プロセスの後半で 2019。 
   
7. **このフロント エンド プールを使用してサーバー ロールの関連付け**] ページで、パイロットのプールの展開中にしない] を選択*して**このフロント エンド プールのメディア コンポーネントで使用する、エッジのプールを有効にします***。 これは、機能を有効にしてオンラインに移行の後の段階でです。 この設定はオフになって今のところを保持します。 
  
8. **Office Web アプリケーション サーバーの選択**] ページで [**新規**作成] をクリックし、アプリケーション サーバーの FQDN を指定します。
  
9. **定義する SQL Server のアーカイブ ストア**] ページで、ビジネス ・ サーバのアーカイブと監視の両方の Skype の SQL Server ストアを定義するときに、ビジネス サーバー 2019 の Skype の前に作成する SQL Server のインスタンスを選択します。 
  
10. トポロジを公開、 **Skype**ビジネス サーバーのノードを右クリックし、**トポロジの公開**] をクリックします。
  
11. 発行プロセスが完了したら、[**完了**] をクリックします。

12. 呼ばれる「レガシ プールと確認試験のプールの共存」の次のセクションに移動する前にする必要がありますビジネス サーバー新しいフロント エンド パイロット プールにだけ公開されているトポロジで定義した Skype のインストールについては、ここで説明した手順[Skype のインストールを実行するためトポロジ内のサーバー上のビジネス サーバー](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)

13. 前の手順の完了後は、レガシ プールとの共存をパイロット プールを確認するのには次のセクションに移動します。
    
<!-- To install a local copy of the configuration store and start the required services, see 
[Setting up Front End Servers and Front End pools for Skype for Business Server 2019](../deployment/deploying-lync-server-2013/setting-up-front-end-servers-and-front-end-pools.md) in the Deployment documentation.  -->
  

