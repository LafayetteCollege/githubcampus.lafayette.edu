---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: page-base
title: GitLab to GitHub Migration Workflow

---

<div class="page-migration">
<p>This workflow describes the steps involved in migrating a repository from the self-hosted campus instance of GitLab to the campus' enterprise account on <a href="http://GitHub.com">GitHub.com</a>.</p>

<h2>Step 1: Create a new repository in your GitHub Organization</h2>

<ol>
<li>While logged into your GitHub account and enterprise shell, go to your Organization and create a new repository.</li>

<li>Complete the following fields:
    <ul>
        <li><strong>Owner:</strong> name of relevant department.</li>
        <li><strong>Repository:</strong> name of the repository.</li>
        <li><strong>Description:</strong> description of repository content and project intent.</li>
        <li><strong>Visibility:</strong> Be sure to select the appropriate visibility, as new repositories are not private by default.
            <ul>
                <li><strong>Public:</strong> world readable. This option is not appropriate for coursework by default, and consent needs to be discussed and negotiated with affected students prior to selecting it.</li>
                <li><strong>Internal:</strong> campus discoverable. Enterprise members logged into the enterprise shell are able to see it.</li>
                <li><strong>Private:</strong> only viewable to a limited number of specific accounts with relevant permissions.</li>
            </ul>
        </li>
        <li>Leave everything else <strong>OFF/ NONE</strong>. The repo should be left totally empty.</li>
    </ul>
</li>
</ol>

<h2>Step 2: Import your GitLab repository into your new GitHub repository</h2>

<p>There are two ways to ingest your GitLab repository into your empty GitHub repository, and which you select depends on whether your repository has many branches.</p>

<h3>Workflow 1: Single Branch Repository</h3>

<ol>
    <li>Make sure all changes have been committed and your local copy of your repository is fully up to date.</li>
    <li><a href="#LocalRemotes">Update your local remotes.</a></li>
</ol>

<h3>Workflow 2: Repository with Multiple Branches</h3>

<ol>
    <li>Make sure all changes have been committed and your local copy of your repository is fully up to date.</li>
    <li>On <a href="http://git.lafayette.edu">git.lafayette.edu</a>, navigate to your repository and click the blue code button, then copy the SSH url to the repository.</li>
    <li>Through Command Line, enter <code>git clone --bare [url]</code> to make a bare clone, replacing <code>[url]</code> with the SSH URL from GitLab.</li>
    <li>Note: There will be no working tree in the new repository. It is cloned as a mirror, not a working copy.</li>
    <li>On GitHub, navigate to your repository and click the green <strong>&lt;&gt;</strong> code button, then copy the URL to your new repository.</li>
    <li>Through Command Line, enter <code>git push --mirror [github url]</code>, replacing <code>[github url]</code> with the URL from GitHub.</li>
    <li>Delete your local mirror using your preferred method.</li>
    <li><a href="#LocalRemotes">Update your local remotes.</a></li>
</ol>

<p>For instructions on creating a mirror repository through GitHub Desktop, see <a href="https://docs.github.com/en/repositories/creating-and-managing-repositories/duplicating-a-repository">GitHub Desktop documentation on duplicating a repository.</a></p>

<hr>

<a name="LocalRemotes" id="LocalRemotes"></a>
<h2>Updating Local Remotes</h2>
<p>This workflow details how to update your local access routes to your remote repositories.</p>

<h3>Update your local remotes via Command Line</h3>
<ol>
    <li>On the Command Line, navigate to the repository for which you need to update your local remotes.</li>
    <li>Enter <code>git remote -v</code> to check current remotes.</li>
    <li>On GitHub, navigate to your repository and click the blue <strong>&lt;&gt;</strong> code button, then copy the URL to your new repository.</li>
    <li>Back on the Command Line, enter <code>git remote set-url origin [github url]</code>, replacing <code>[github url]</code> with the URL copied from GitHub.</li>
    <li>Check <code>git remote -v</code> again to ensure that <strong>fetch</strong> and <strong>push</strong> have updated to the new GitHub links.</li>
    <li>Test the update with a simple pushed update.</li>
</ol>

<h3>Update your local remotes via GitHub Desktop</h3>
<p><a href="https://docs.github.com/en/desktop/working-with-your-remote-repository-on-github-or-github-enterprise/changing-the-remote-url-for-a-repository-in-github-desktop">Review GitHub Documentation for instructions updating remotes through GitHub Desktop</a></p>
</div>

