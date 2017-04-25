desc "Install dependencies"
task :deps do
  exec "ansible-galaxy install --ignore-errors --force " \
    " --role-file=.dependencies.yml"
end

desc "Install common utitilies"
task :common do
  exec "ansible-playbook 001_common_utilities.yml"
end

desc "Install docker"
task :docker do
  exec "ansible-playbook 004_docker.yml"
end

desc "Install Ajenti"
task :ajenti do
  exec "ansible-playbook 009_ajenti.yml"
end

desc "Install GitLab server"
task :gitlab do
  exec "ansible-playbook 010_gitlab.yml -l gitlab"
end

desc "Install Jenkins server"
task :jenkins do
  exec "ansible-playbook 011_jenkins.yml -l jenkins"
end

desc "Install Gogs server"
task :gogs do
  exec "ansible-playbook 013_gogs.yml -l gogs"
end

desc "Disable Registration of Gogs"
task :gogsdr do
  exec "ansible-playbook 014_gogs_disable_registration.yml --tags=config,wait,restart -l gogs"
end

desc "Install Ghost server"
task :ghost do
  exec "ansible-playbook 030_ghost.yml -l ghost"
end

desc "Install shadowsocks server"
task :shadowsocks do
  exec "ansible-playbook 022_shadowsocks.yml -l shadowsocks"
end

desc "Install haproxy server"
task :haproxy do
  exec "ansible-playbook 023_haproxy.yml"
end

desc "Install uptime"
task :uptime do
  exec "ansible-playbook 059_uptime.yml -l uptime"
end

desc "Install Huginn"
task :huginn do
  exec "ansible-playbook 060_huginn.yml -l huginn"
end

desc "Test Ubuntu"
task :test_ubuntu do
  system "vagrant up ubuntu --no-provision"
  system "vagrant provision ubuntu"
end

desc "Test Debian"
task :test_debian do
  system "vagrant up debian --no-provision"
  system "vagrant provision debian"
end

task :default => [:common]
