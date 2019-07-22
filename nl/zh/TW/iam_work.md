---

copyright:
  years:  2018, 2019
lastupdated: "2019-03-06"

keywords: Sysdig, IBM Cloud, monitoring, iam, access groups

subcollection: Sysdig

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:pre: .pre}
{:table: .aria-labeledby="caption"}
{:codeblock: .codeblock}
{:tip: .tip}
{:download: .download}
{:important: .important}
{:note: .note}

 
# 使用 IAM 原則及存取群組
{: #iam_work}

{{site.data.keyword.iamlong}} (IAM) 可讓您在 {{site.data.keyword.cloud_notm}} 中，安全地鑑別使用者以及一致地控制對所有雲端資源的存取。
{:shortdesc}

若要將 Sysdig 管理者專用權授與使用者，您可以將下列任何角色指派給使用者：

* `管理者`平台角色：如果使用者也是 {{site.data.keyword.cloud_notm}} 中 Sysdig 服務的管理者，請授與此角色。
* `編輯者`平台角色：如果使用者必須能夠在 {{site.data.keyword.cloud_notm}} 佈建或移除 Sysdig 實例，請授與此角色。
* `管理員`服務角色：如果使用者不能在 {{site.data.keyword.cloud_notm}} 管理 Sysdig 服務，請授與此角色。

若要將 Sysdig 使用者專用權授與使用者，您可以將`撰寫者`服務角色指派給使用者。

**附註：**若要透過使用 IAM 原則來管理存取權或指派使用者的新存取權，您必須是帳戶擁有者、帳戶中所有服務的管理者，或特定服務或服務實例的管理者。 

作為**帳戶擁有者**或 **{{site.data.keyword.mon_full_notm}} 服務管理者**，您必須具有許可權來執行下列平台動作： 

* 授與其他帳戶成員使用服務的存取權
* 佈建服務實例
* 刪除服務實例
* 檢視服務實例的詳細資料
* 建立服務 ID

作為 **Devops 使用者**，您必須具有許可權來執行下列平台動作： 

* 佈建服務實例
* 刪除服務實例
* 檢視服務實例的詳細資料
* 建立服務 ID


## 將許可權授與使用者，以變成 {{site.data.keyword.cloud_notm}} 帳戶中服務的管理者
{: #admin_account}

若要授與使用者管理者角色來管理帳戶中的服務，使用者必須具有平台角色**管理者**對 {{site.data.keyword.mon_full_notm}} 服務的 IAM 原則。您必須將帳戶中個別資源的存取權指派給這個使用者。 

請完成下列步驟，將帳戶中 {{site.data.keyword.mon_full_notm}} 服務的管理者角色，指派給使用者： 

1. 從功能表列中，按一下**管理** &gt; **存取權 (IAM)**，然後選取**使用者**。
2. 從您要指派存取權的使用者列中，選取**動作**功能表，然後按一下**指派存取權**。
3. 選取**指派對資源的存取權**。
4. 選取 **{{site.data.keyword.mon_full_notm}}**。
5. 選取**所有現行地區**。
6. 選取**所有現行服務實例**。
7. 選取平台角色**管理者**。
8. 按一下「指派」。


## 將許可權授與使用者，以變成資源群組內服務的管理者
{: #admin_rg}

若要授與使用者管理者角色來管理帳戶中資源群組內的實例，使用者在該資源群組的環境定義內，必須具有平台角色**管理者**對 {{site.data.keyword.mon_full_notm}} 服務的 IAM 原則。 

請完成下列步驟，將資源群組環境定義內 {{site.data.keyword.mon_full_notm}} 服務的管理者角色，指派給使用者： 

1. 從功能表列中，按一下**管理** &gt; **存取權 (IAM)**，然後選取**使用者**。
2. 從您要指派存取權的使用者列中，選取**動作**功能表，然後按一下**指派存取權**。
3. 選取**指派資源群組內的存取權**。
4. 選取資源群組。
5. 如果未授與使用者所選資源群組的角色，請針對**指派資源群組的存取權**欄位，選擇一個角色。 

    視您選取的角色而定，使用者可以在其儀表板上檢視資源群組、編輯資源群組名稱，或管理群組的使用者存取權。 
    
    如果您希望使用者只具有資源群組中對 {{site.data.keyword.mon_full_notm}} 服務的存取權，可以選取**不存取**。

6. 選取 **{{site.data.keyword.mon_full_notm}}**。
7. 選取平台角色**管理者**。
8. 按一下**指派**。


## 將許可權授與 Devops 使用者，以管理 {{site.data.keyword.cloud_notm}} 帳戶中的服務
{: #devops_account}

您需要平台角色**編輯者**對 {{site.data.keyword.mon_full_notm}} 服務的 IAM 原則。

請完成下列步驟，將使用者編輯者角色指派給帳戶中的 {{site.data.keyword.mon_full_notm}} 服務： 

1. 從功能表列中，按一下**管理** &gt; **存取權 (IAM)**，然後選取**使用者**。
2. 從您要指派存取權的使用者列中，選取**動作**功能表，然後按一下**指派存取權**。
3. 選取**指派對資源的存取權**。
4. 選取 **{{site.data.keyword.mon_full_notm}}**。
5. 選取**所有服務實例**。
6. 選取平台角色**編輯者**。
7. 按一下「指派」。

## 將許可權授與 Devops 使用者，以管理 {{site.data.keyword.cloud_notm}} 帳戶中的實例
{: #devops_account_instance}

請完成下列步驟，將使用者編輯者角色指派給帳戶中的某個 {{site.data.keyword.mon_full_notm}} 服務實例： 

1. 從功能表列中，按一下**管理** &gt; **存取權 (IAM)**，然後選取**使用者**。
2. 從您要指派存取權的使用者列中，選取**動作**功能表，然後按一下**指派存取權**。
3. 選取**指派對資源的存取權**。
4. 選取 **{{site.data.keyword.mon_full_notm}}**。
5. 選取實例。
6. 選取平台角色**編輯者**。
7. 按一下「指派」。



## 將許可權授與 Devops 使用者，以管理資源群組內的服務
{: #devops_rg}

您需要平台角色**編輯者**對 {{site.data.keyword.mon_full_notm}} 服務的 IAM 原則。

請完成下列步驟，將資源群組環境定義內 {{site.data.keyword.mon_full_notm}} 服務的編輯者角色，指派給使用者： 

1. 從功能表列中，按一下**管理** &gt; **存取權 (IAM)**，然後選取**使用者**。
2. 從您要指派存取權的使用者列中，選取**動作**功能表，然後按一下**指派存取權**。
3. 選取**指派資源群組內的存取權**。
4. 選取資源群組。
5. 如果未授與使用者所選資源群組的角色，請針對**指派資源群組的存取權**欄位，選擇一個角色。 

    視您選取的角色而定，使用者可以在其儀表板上檢視資源群組、編輯資源群組名稱，或管理群組的使用者存取權。 
    
    如果您希望使用者只具有資源群組中對 {{site.data.keyword.mon_full_notm}} 服務的存取權，可以選取**不存取**。

6. 選取 **{{site.data.keyword.mon_full_notm}}**。
7. 選取平台角色**編輯者**。
8. 按一下**指派**。

## 授與許可權以在 Sysdig 管理度量值及配置警示
{: #admin_user_sysdig}

作為 Sysdig 中的 **admin 使用者**，您必須具有執行下列動作所需的許可權： 

* 新增度量值來源
* 檢視度量值
* 搜尋度量值
* 過濾度量值
* 配置警示

因此，您需要下列原則：

* 平台角色為**編輯者**對 {{site.data.keyword.mon_full_notm}} 服務的 IAM 原則。此原則可讓您透過指令行及在 {{site.data.keyword.cloud_notm}} 儀表板中檢視服務實例詳細資料。
* 服務角色為**管理員**對 {{site.data.keyword.mon_full_notm}} 服務的 IAM 原則。此原則可讓您透過 Sysdig Web 使用者介面來監視、過濾及搜尋度量值，以及定義警示。

**附註：**身為服務管理者，當您授與使用者這些原則時，請考量在資源群組的環境定義內執行此動作。{{site.data.keyword.mon_full_notm}} 實例佈建在資源群組的環境定義內。因此，您應該在資源群組的環境定義內授與存取權。


請完成下列步驟，將資源群組環境定義內 {{site.data.keyword.mon_full_notm}} 服務的這兩個原則，指派給使用者： 

1. 從功能表列中，按一下**管理** &gt; **存取權 (IAM)**，然後選取**使用者**。
2. 從您要指派存取權的使用者列中，選取**動作**功能表，然後按一下**指派存取權**。
3. 選取**指派資源群組內的存取權**。
4. 選取資源群組。
5. 如果未授與使用者所選資源群組的角色，請針對**指派資源群組的存取權**欄位，選擇一個角色。 

    視您選取的角色而定，使用者可以在其儀表板上檢視資源群組、編輯資源群組名稱，或管理群組的使用者存取權。 
    
    如果您希望使用者只具有資源群組中對 {{site.data.keyword.mon_full_notm}} 服務的存取權，可以選取**不存取**。

6. 選取 **{{site.data.keyword.mon_full_notm}}**。
7. 選取平台角色**編輯者**。
8. 選取服務角色**管理員**。
8. 按一下**指派**。

## 將許可權授與使用者以在 Sysdig 中檢視度量值
{: #user_sysdig}

作為**使用者**、**審核員**或**開發人員**，您可能需要許可權來執行下列動作： 

* 檢視度量值
* 搜尋度量值
* 過濾度量值

因此，您需要下列原則：

* 平台角色為**檢視者**對 {{site.data.keyword.mon_full_notm}} 服務的 IAM 原則。此原則可讓您透過指令行及在 {{site.data.keyword.cloud_notm}} 儀表板中檢視服務實例詳細資料。
* 服務角色為**撰寫者**對 {{site.data.keyword.mon_full_notm}} 服務的 IAM 原則。此原則可讓您透過 Sysdig Web 使用者介面來檢視、過濾及搜尋度量值。

**附註：**作為服務的管理者，當您授與使用者這些原則時，請考慮在資源群組的環境定義內執行操作。{{site.data.keyword.mon_full_notm}} 實例佈建在資源群組的環境定義內。因此，您應該在資源群組的環境定義內授與存取權。

請完成下列步驟，將資源群組環境定義內 {{site.data.keyword.mon_full_notm}} 服務的這兩個原則，指派給使用者： 

1. 從功能表列中，按一下**管理** &gt; **存取權 (IAM)**，然後選取**使用者**。
2. 從您要指派存取權的使用者列中，選取**動作**功能表，然後按一下**指派存取權**。
3. 選取**指派資源群組內的存取權**。
4. 選取資源群組。
5. 如果未授與使用者所選資源群組的角色，請針對**指派資源群組的存取權**欄位，選擇一個角色。 

    視您選取的角色而定，使用者可以在其儀表板上檢視資源群組、編輯資源群組名稱，或管理群組的使用者存取權。 
    
    如果您希望使用者只具有資源群組中對 {{site.data.keyword.mon_full_notm}} 服務的存取權，可以選取**不存取**。

6. 選取 **{{site.data.keyword.mon_full_notm}}**。
7. 選取平台角色**檢視者**。
8. 選取服務角色**撰寫者**。
8. 按一下**指派**。
