#oppna-program-reklistna-workflows


## main-workflow.xml

### Setup

#### 1. Upload the workflow to the site
Control Panel > Workflows > Upload Definition. Upload the XML.

#### 2. Add custom field
The workflow will assign the article to a _role_ and that role is set on each article. To be able to do this we need to add an expando field to Web Content Articles.

Go to Control Panel > Configuration > Custom Fields. Add a new custom field to `Web Content Article`:

* Key: `reviewer-role`
* Type: `Text Field - Indexed`

There's a Liferay bug which has this effect:
When a user which does _not_ have update permissions to a custom field on a journal article updates the article, any previously set custom field value is removed. Therefor we need to give the user rights to update the custom field. To do that, click Actions > Permissions and add `Update` to the "User" Role.

#### 3. Set role to article
Go to an article, edit it. Click "Custom Fields" in the menu to the right. In the "Reviewer Role" input, enter the _name_ of the Role to which you want this article to be assigned. Rinse and repeat for every article.

#### 4. Configure site to use workflow
Control Panel > {your site} > Configuration > Workflow Configuration. Set `Web Content Article` to use the workflow.
